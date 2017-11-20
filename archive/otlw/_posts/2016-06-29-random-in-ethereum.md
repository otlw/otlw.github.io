---
layout: post
title: "Random in Ethereum"
---
Randomness is notoriously difficult to obtain in Ethereum, a fact that was noted quickly since gambling was about the second thing anyone wanted to build. After world changing applications for new societies of course.

The problem lies in the fact that all miners have to obtain the same result to be able to determine its validity and commit it to the chain. Ethereum is a blockchain + a deterministic Turing machine, meaning there is no randomness involved. If there was a random opcode in place, all miners would obtain different results and the network would be unable to reach a consensus.

Naturally however, we have some workarounds. Each has their upsides and down, and their quirks and features.

# The Blockhash
The first source that springs to mind is blockhashes. They are essentially unpredictable and completely contained on chain, which makes them very easily accessible. One can then use that blockhash as a seed for random functions. This is a [simple generator](https://gist.github.com/alexvandesande/259b4ffb581493ec0a1c) written by Alex van de Sande; we use a similar function in [otlw-assess](https://github.com/otlw/otlw-assess).

```
contract random {
    /* Generates a random number from 0 to 100 based on the last block hash */
    function randomGen(uint seed) constant returns (uint randomNumber) {
        return(uint(sha3(block.blockhash(block.number-1), seed ))%100);
    }

    /* generates a number from 0 to 2^n based on the last n blocks */
    function multiBlockRandomGen(uint seed, uint size)
      constant returns (uint randomNumber) {
        uint n = 0;
        for (uint i = 0; i < size; i++){
            if (uint(sha3(block.blockhash(block.number-i-1), seed ))%2==0)
                n += 2**i;
        }
        return n;
    }
}
```
However, this is not entirely secure. The problem lies in the fact that miners have limited control over blockhashes, as they can choose whether or not to publish a block. By withholding a miner could exert their influence over the random function, and because of Ethereum’s deterministic nature, a miner can be very knowledgeable on the outcome if they do publish a mined block.
As such, to be economically viable. the reward at stake in any random dependent function must not exceed the mining reward. In situations where that criteria is met, block hashes can work very well, cleanly and simply.

# Oracles
For times when things aren’t so clear cut we have “messy” solution: **Oracles**

These services essentially provide a link to webservices outside the Ethereum network. So one could use it to access sources of random data through services like WolframAlpha, or random.org.

![Oracalize.it flowchart](http://docs.oraclize.it/images/flowchart.png)

There are obviously several points of failure. You have to have confidence in the Oracle you are using, and in both the validity and security of any random sources. Beyond this trust, however, there are difficulties.
Because of the nature of oracles they cannot directly return any requested value; they have to use **callbacks**. You first must call the random function, wait for it to communicate with the servers, then, a block or more later, it will trigger another function, passing the given value.

```
/*
   Simple "roll a Dice".

   After calling the "bet" method along with 1 wei,
   the contract asks Wolfram Alpha to roll a dice.
   You get back either 0 wei or 2.
*/

import "dev.oraclize.it/api.sol";

contract SimpleDice is usingOraclize {
    address owner;
    mapping (bytes32 => address) bets;

    function Lottery(){
        owner = msg.sender;
    }

    function __callback(bytes32 myid, string result) {
        if (msg.sender != oraclize_cbAddress()) throw;
        if (uint(bytes(result)[0]) - 48 > 3) bets[myid].send(2);
    }

    function bet(){
        if ((msg.value != 1)||(this.balance < 2)) throw;
        rollDice();
    }

    function rollDice() {
        bytes32 id = oraclize_query(0,"WolframAlpha","random number from 1 to 6");
        bets[id] = msg.sender;
    }

    function kill(){
        if (msg.sender == owner) suicide(msg.sender);
    }
}
```
This is an [example](https://github.com/oraclize/ethereum-examples/blob/master/solidity/SimpleDice.sol) contract from Oracalize implementing a simple dice function. Here the callback is fairly simple, depending on the result of the call it either sends 2 ether or not. However, in larger contracts callbacks can get more complex and impose a structural and gas-cost burden on your DApp. This can be worsened by the need to depend on TLSNotary proofs, which maintain the security of your calls. Overall however, if implemented properly, this can be more dependable and far less prone to malleability than blockhashes.

# The Grail
There is something approaching a holy grail of Randomization in Ethereum, something both secure and on chain. It also happens to be a very eth-y solution, embracing economic incentives and decentralization. It’s the [RanDAO](https://github.com/randao/randao). It’s a DAO (Decentralized Autonomous Organization, though everyone probably knows what that is by now) that facilitates the generation of random numbers in a fixed cycle. It consists of at least 3 stages, where valid SHA3 hashes are committed, revealed, and combined to create a single random number. Participants are rewarded to incentivize contribution. It’s a pretty neat, if complex solution, but it does have its downsides. Numbers have to be created in a fixed cycle rather than on demand, which could prove as structurally influential to a DApp as an oracle callback. More importantly however, it requires widespread use and adoption to become dependable.

This is where work still needs to be done. Right now, we’ve built a tentative solution using blockhashes (with some extra steps in place to make sure it can’t be abused) for our own project. But the ideal solution would be a network scale ranDAO, with improvements like those [suggested](https://www.reddit.com/r/ethereum/comments/4mdkku/could_ethereum_do_this_better_tor_project_is/d3v6djb) by Vitalik, adopted and run, perhaps, by miners. There has to be a community wide push for this. It’ll enable DApps far more valuable than simply another Casino Contract, and will help develop the infrastructure needed for the platform to fully mature and live up to its potential, bringing secure and powerful randomness to the rest of the world.

# Random and the world
Whether we like it or not this kind of randomness plays a huge role in the function and progress of out society. Of course we might not like it, as it grates against our normal sensibilities of order and meaning. But it’s inescapable because, unlike the majority of human proceedings, randomness is provably fair. It, somewhat counter-intuitively, introduces control and focus.

Because of this, randomness crops up in areas where we try to approach the singular truth of a matter, such as scientific trials, or legal juries. Drawing randomly from a population allows us to isolate the relevant traits of that population from traits any single individual in it might posses. With a jury we are trying to isolate the population’s judgement of a certain situation. With a randomized trial in pharmaceuticals we are trying to isolate the relevant properties of a drug. Law and the Scientific Method, are two critical developments, essential to the foundation of our society, and it’s of the utmost importance that their integrity is maintained.

When that integrity is violated, major problems can arise. Unjust juries can lead to decades long failures in legal systems, fudged trials can result in billions of dollars of damages, and even things as simple as bad polling can transform political landscapes. If randomness is compromised it can lead to large scale failures undermining the entirety of the systems these events occur in. More often than not these failures are a result of oversight, or deliberate action, from a central party, violating the fairness of a system.

# Where Ethereum Comes In
Decentralization and provable fairness; both are essential parts of the appeal of Ethereum. It’s a system that one can always trust to function exactly as expected to, and as such, is a perfect match for the societal applications of randomness. Systems for juries, for scientific research, for polling, based on Ethereum, would be incredibly powerful indeed.

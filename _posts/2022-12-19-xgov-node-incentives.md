---
layout: post
title: Why I Am Against Online Stake Becoming an ALGO xGov Requirment
---

Last week, the Algorand Foundation [posted an ARC](https://github.com/algorandfoundation/ARCs/pull/152) to begin discussion on the xGov process. xGovs will be a key part in a decentralized governance system for Algorand, as they will be the ones pushing forward proposals for the governors to vote on. One of the topics being discussed is whether or not having online stake should be a requirement for becoming an xGov. The idea is that this will improve the decentralization of the network by incentivizing people to take their stake online, but there are a lot of problems with this proposal.

# Key Beliefs
Before going into the reasoning for why I do not support the idea of online stake being a xGov requirement, I want to lay out some key beliefs that frame my opinion.

## Governance is more fundamental than consensus

Some have argued that participation is the most important part of a blockchain network and as such it should be a requirement for participation in governance. While I agree at a technical level, the governance of a network is ultimately more fundamental than consensus for one simple reason: governance can change consensus, but it's rare for the opposite to occur. 

A good case study for this is Bitcoin (BTC) and the blocksize wars that took place a couple of years ago. To give some context, the blocksize wars was a heated debate between two sides of the BTC community:

* Big blockers
	* Wanted bigger block sizes
	* Wanted to increase usability: lower fees and quicker transactions
	* Popular initial proposal was 8MB blocks
* Small blockers
	* Wanted to maintain the small (1MB) block size
	* Wanted to preserve decentralization by keeping node requirements as low as possible

The full story of the blockchain wars is a fascinating one, but I will instead be focusing on the portion of the story around segwit2x. segwit2x was a compromise (depending on who you ask) between the two sides of the wars. It introduced 4MB blocks alongside Segregated Witness, a new transaction format that allowed for more efficient inclusion of transactions in blocks. At one point, [80% of miners indicated support for segwit2x](https://cointelegraph.com/news/segwait-is-over-bitcoin-network-shows-80-percent-support-for-segwit2x)... but it was ultimately never implemented, at least not in the network we still call BTC. 

If 80% of miners supported segwit2x, how is it possible that the network never implemented it? Centralized entities, such as exchanges, started to reject segwit2x completely or attempted to sit the fence and support both segwit2x and non-segwit2x chains. Ultimately, the developers behind BTC Core, the primary software for participating in the BTC network, made it clear they weren't going to support segwit2x which was the final nail in the coffin. 

You might be asking, "why wasn't there simply a segwit2x fork and a non-segwit2x fork?" This did technically happen, but the segwit2x fork saw such little node and transaction activity it was not worth mining. Most people who were in support of segwit2x [left BTC for Bitcoin Cash (BCH)](https://www.reddit.com/r/btc/comments/7bmp4u/segwit2x_canceled/), a popular fork of BTC that forked away from the network prior to the segwit2x debacle. This highlights the core problem with leaning on consensus as a form of governance: a disagreement in governance is much more likely to result in users/nodes leaving for other chains rather than resulting in two forks of the original chain. This is even more true now than it was for BTC given the competitive landscape of various L1/L2 solutions and the key role of foundations in chain adoption. 


## Node incentives aren't needed long-term

I believe node incentives can help grow a blockchain in its early stages, but I do not believe they are necessary long term. I will return to BTC as a useful case study. While it's true that BTC miners are directly incentivized to create and hash new blocks, the rest of participation is not incentivized. As of the time of this post, there are nearly 15,000 nodes validating and propagating transactions and blocks. None of these nodes are incentivized yet they are largely responsible for the liveness and security of the network. 

While it is evident incentives aren't necessary for a chain to operate, they are helpful in the early growth of a chain. Unlike BTC, new chains such as Algorand see a rapid expansion in adoption that is disproportional to the size of the network itself. This creates potential imbalances in the ratio of on-chain value to on-chain security. The theory is that those with a lot of stake in the network will run a node to protect their stake, but the reality is that this is hard to achieve at such early stages in a blockchain. This is where short term incentives can be useful, but they should not overstay their welcome. 

## Blockchain governance should be equitable

The commonly repeated mission of blockchain is to "bank the unbanked." The idea is to give everyone equitable access to various financial instruments across the globe. Implementing a governance model that doesn't strive towards equitable access is counter-productive to the ethos of blockchain technology. As such, anything that makes a clear divide between "haves" and "have nots" in governance is not ideal and should be heavily considered before implementation. 

# Potential Incentive Scenarios
## xGov requirement without financial incentives

In this scenario, let's imagine what the network would look like if online stake was a requirement for xGovs, but nodes were not incentivized financially. There are really two sub-scenarios that could play out:

1. Node runners allow delegation for free, meaning anyone can take their stake online for free
2. Node runners charge for delegation, meaning anyone wanting to take their stake online must pay for delegation (or pay the cost of running a node)

The first scenario is rather unrealistic because it assumes there will be altruistic node runners that will give away compute power and energy for free. Even if we entertain this being a realistic possibility, it is far from ideal. Free delegation means that most rational users will choose to delegate their participation key to a node runner for free rather than paying the costs of operating a node themselves. This ultimately leads to centralization and since the node runners are not profiting from delegation, they have no incentive to act in the interest of the delegators. 

The second scenario assumes that people will be willing to pay to take their stake online and participate in governance as an xGov. The entire reason we are having this discussion is because the assumption of altruistic participants running a node for free isn't working right now... so now we are expecting the same people being willing to pay to take their stake online? It just doesn't make sense given the original problem we are trying to solve. 

## Financial incentives without xGov requirement

When financial incentives are introduced, the landscape for node runners and delegators is changed quite dramatically. First, we have the obvious happen: more people start to run nodes because they can make money doing so. If rewards are proportional to stake, there is also the additional benefit of honest node runners holding more online stake to increase profits. With financial incentives, it also becomes much more reasonable for node runners to charge for delegation. Delegators are willing to pay because they can get a ROI from their stake. Node runners are incentivized to to act benevolently (or at least in the interest of their delegators) because they are making a profit off them. 

## xGov requirement with financial incentives

At this point, I think it's clear that financial incentives can help grow the network, so why do we also need to introduce the xGov requirement as an incentive? This is a question that has yet to be answered clearly. Making it a requirement introduces two problems:

1. It creates a clear barrier of entry that might be hard for some to overcome
2. It introduces bias in the xGov process

The first problem is straight forward. Running a node requires time, money, and technical knowledge which not all stakeholders have. The obvious retort is delegation, but if we operate under the assumption that financial incentives will be temporary if implemented, this will create a significant barrier once delegation is no longer a reasonable option.  You might ask, "why not have the requirement be temporary?" This leads us to the second problem... If all the xGovs are node runners or delegators, there will be a bias in the system towards benefitting them. They might be incentivized to push through proposals that benefit themselves but not the network. In the context of the first problem, why would they support proposals that take away their own power? If it's not a necessary incentive, especially long term, why introduce this risk of bias into the governance system?

# Conclusion

Assuming the three above scenarios are decent representations of how things might play out, it's clear that either scenario involving online stake being an xGov requirement is not ideal. Best case is bias being introduced into the xGov process and worst case is centralization of stake with no accountability of node runners. I am not against against incentives in general, but I believe temporary financial incentives are the best way to incentivize nodes and improve the decentralization of the network while maintaining an equitable governance process.  
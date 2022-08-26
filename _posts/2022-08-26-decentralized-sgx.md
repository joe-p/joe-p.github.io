---
layout: post
title: Privacy Blockchains Are Too Good to Be True
subtitle: Intel SGX doesn't belong on decentralized networks
comments: true
---

A couple of weeks ago I came across [a post](https://np.reddit.com/r/CryptoCurrency/comments/wcdfg1/oasis_network_why_you_should_really_be_paying/) on /r/CryptoCurrency titled "Oasis Network - why you should REALLY be paying attention if you like privacy & data ownership". As someone that finds privacy and data ownership important, the title intrigued me enough to read through the post. The fact that they partnered with Meta was what first caught my eye, but their claim of privacy on a blockchain is what pulled me down the rabbit hole. My initial impression was that it seemed too good to be true. In this blog post I'll explain why it really is too good to be true.

# What's The Claim?

Due to the nature of blockchains, everything done on-chain can be seen by anyone. This means blockchains, in their current state, are not a good solution for anything that requires data privacy (not counting transaction privacy like zcash or monero). Some chains, however, lead users to believe that this isn't the case. They claim that they can leverage something called Trusted Executable Environments (TEEs) on nodes in the network to preserve privacy. The most common TEE is Intel SGX, which is what Oasis and Secret Network use. 

# What Is a Trusted Executable Environment?

In short, TEEs are a way for computers to run software that can't be seen or manipulated by anyone. When software is executing in a TEE, the entire program and the memory it uses is considered to be in an enclave. An enclave is resources of a computer system which is completely separated from the rest of the system. When memory in the enclave is being used, nothing outside of the enclave can see or modify the data (not even the kernel). This effectively makes an enclave a computational black box. 

# How Do Blockchains Use Trusted Executable Environments?

A blockchain network is composed of a bunch of computers, or nodes, running some software to perform computations and validations for the network. With most chains, anyone running a node can see and control what data goes in and what data goes out. When using a TEE, an encrypted message is sent to the the enclave on a node. In the enclave the encrypted message is decrypted and computations are ran on the data privately. What comes out is some sort of attestation to what the result of the computation was. There is (theoretically) no way for the node-runner to see what the data going into the black box is and no way to manipulate the computation.

# What’s the Problem?

### The Lesser Problem: Centralization
 
It is crucial for blockchain networks to be as decentralized as possible. The introduction of Intel SGX as a core technology for these blockchains adds a significant component of centralization to these networks. Intel SGX is proprietary. If Intel decides to stop supporting it, networks that leverage will be screwed. Best case scenario they require nodes to run old hardware, but that still leaves them open to any future exploits that might be discovered. 

The good news for this problem is that there are alternative TEEs out there for various platforms, some of which are even open-source. They all, however, unfortunately fall victim to the second problem...

### The Bigger Problem: Security

Centralization is not ideal, but you could make the argument that it is an inevitable growing pain for blockchains. The real problem lies within the security model of Intel SGX (and other TEEs). For starters, there have been multiple Intel SGX vulnerabilities since the inception of the technology. Most of these vulnerabilities have been given cools names like [SmashEx](https://www.tomshardware.com/news/smashex-attack-targets-intel-sgx) and [Plundervolt](https://www.zdnet.com/article/new-plundervolt-attack-impacts-intel-cpus/)). Generally Intel is able to patch the vulnerabilities, but in the context of a decentralized network you can't expect every node runner to immediately update to the latest patches. 

An even bigger problem than the exploits themselves is Intel's threat model. In 2020, a new vulnerability called [VoltPillager](https://www.phoronix.com/news/VoltPillager-HW-Undervolt) was discovered. At this point, an Intel SGX vulnerability isn't all too surprising. The more shocking part of this story, however, is Intel's response to the vulnerability. The following is from the [original VoltPillager paper](https://www.usenix.org/system/files/sec21-chen-zitai.pdf):

> We reported this issue to Intel on 13 March 2020. Intel evaluated our report and concluded on 5 May that “... opening the case and tampering of internal hardware to compromise SGX is out of scope for SGX threat model. Patches for CVE-2019-11157 (Plundervolt) were not designed to protect against hardware-based attacks as per the threat model”, and, therefore, they will not further address the issue.

Intel has made it clear that physical access to the system is not part of their security model. As such, securely using Intel SGX requires two things:

1. Patches are applied as quickly as possible
2. Malicious parties cannot have access to the hardware

In the context of blockchain networks where anyone can run a node, the first requirement is a bold assumption to make and the second requirement is simply impossible to achieve. 

# Exploits in a Privacy Network

With a typical blockchain network, the security of the network grows as the network gets bigger. With privacy networks using TEEs, however, the network will become less and less secure as it grows. Each node is adding to the potential attack surface. All it takes is one malicious actor to run a node and exploit a vulnerability to get access to the enclave's memory, or worse, the enclave's key used for decrypting or signing data. Once this happens, all privacy goes out the window. End-users can no longer trust that their private information will be kept private. For certain pieces of data, such as bank account information, a loss of privacy is absolutely devastating for the end-user. Again, all it would take is a single malicious actor to put this sort of data at risk. 

# The Solution?

At this point, I hope it's clear why decentralized networks leveraging Intel SGX, or any TEE, to provide privacy are too good to be true. That leaves the question, "what is true?" Unfortunately, right now the truth seems to be that decentralized privacy is a really hard problem to solve. Fortunately, decentralized privacy being a hard problem doesn't mean it's an impossible problem. There are some potential solutions, such as homomorphic encryption, but much like TEEs all it takes is one bad actor with one exploit to compromise the entire network's purpose. Thus, it will likely be awhile before we see true production-ready solutions. Until then, be sure to do your own research before using (or investing) in any technology that seems to good to be true.

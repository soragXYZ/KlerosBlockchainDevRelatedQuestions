# Blockchain dev related questions

## 1) Blockchain consensus
What is:
- Proof-of-Work?  

Proof-of-work (PoW) is a consensus mechanism used by blockchain networks to achieve distributed consensus. It is used to confirm transactions and produce new blocks to the chain.  

In a PoW-based blockchain, nodes compete to solve a complex mathematical problem, and the first one to solve it gets to add a new block to the chain and receives a reward for doing so. The process of solving the mathematical problem is computationally expensive, and requires significant amounts of computational power. The complexity of the problem is such that it can only be solved by brute force, meaning that it cannot be solved by any other means than trying many possible solutions. Because of this, it is very difficult to cheat the system.  

The idea behind PoW is that it is costly to produce a new block and therefore, it prevents malicious actors from easily taking over the network by creating multiple blocks in quick succession. This ensures that the network remains decentralized and secure.  

- Proof-of-Stake?  

Proof-of-stake (PoS) is an alternative consensus mechanism used by some blockchain networks to achieve distributed consensus. The nodes that are allowed to add new blocks to the chain are chosen based on their stake, or the amount of cryptocurrency they hold and are willing to lock up or "stake" as collateral.  

The idea behind PoS is that, instead of expending energy to mine new blocks, nodes can validate transactions and add new blocks to the chain by holding and "staking" cryptocurrency. The more cryptocurrency a node holds and is willing to stake, the higher its chances of being chosen to add a new block to the chain.  

In PoS, there are validators who are chosen to create new blocks, and they are chosen randomly among the holders based on the proportion of their holding compared to the total stake. When a validator is chosen, it will validate the transactions and create a new block, and in return, it will get rewarded.  

One of the key benefits of PoS over PoW is that it is more energy efficient, since it doesn't require miners to perform computational work. This means that it is less costly to run a PoS-based blockchain network.  

- Proof-of-Authority?  

Proof of Authority (PoA) is a consensus mechanism used by some blockchain networks to achieve distributed consensus. It is similar to Proof of Stake (PoS) in the sense that the nodes that are allowed to add new blocks to the chain are chosen based on their authority or reputation, rather than on the amount of cryptocurrency they hold and are willing to lock up.  

In PoA, the validators are pre-selected and authorized by the network's governance or by a central authority, and they are responsible for validating transactions and creating new blocks. These validators are known, identifiable individuals or organizations that have been vetted and approved by the network's governance or central authority to ensure that they are trustworthy and reliable.  

PoA is used primarily in private or consortium blockchain networks, where the network participants are known and trusted entities such as government agencies, financial institutions, and other organizations. In PoA, the security of the network is maintained by the reputation and trustworthiness of the validators, rather than by the computational power of the network.  

PoA networks are less decentralized than public networks like Bitcoin or Ethereum, but they are more suitable for use cases that require a high degree of trust, such as supply chain management, digital identity verification, and other enterprise use cases.  

- Proof-of-X? (with X being a consensus mechanism not previously explained)  

Proof-of-X is a general term used to refer to any consensus mechanism that uses a specific method or rule to achieve distributed consensus. "X" can represent any consensus algorithm or rule, and it can be used to create new consensus mechanisms or to describe existing ones.  


## 2) Hashes
In a blockchain system, in the first step party A must commit to n values X={x_1,x_2,...,x_n}.  
Note that it is important that the values can’t be known by a blockchain observer before party A reveals them.  
To do so we define the hash chain as y_1=x_1 and y_n=hash(x_n,y_{n-1}) for n=2,...,n.
Where hash is a cryptographic hash function with the following properties:
Preimage resistance (From a value b, it is computationally impossible to find a, such that hash(a)=b).
Collision resistance (It is computationally impossible to find a_1 and a_2 such that hash(a_1)=hash(a_2)).  


In a first step party A sends a transaction containing y_n.  
In the second step, party A reveals one of these values.  Note that at this point, it is not a problem if some observer knows the values revealed.  

What is the computational complexity of the reveal operation:  
- For party A?  

The computational complexity of the reveal operation is O(n)  

- For every fullnode of the blockchain (this is linked to gas consumption)?  

The computational complexity for every fullnode of the blockchain is O(n^2) 


- Can we use another data structure to reduce the computational complexity for every fullnode (when you want to reveal just 1 value), without increasing the complexity of the commit operation? If it is, what is this data structure and what would be the resulting complexity?  

I do not know  

Assuming that n=5 and x_i in {0,1}. Is it possible for an external observer to determine X from y_5 in the first step? If it is, how can we change the scheme to prevent it?  

I do not know



## 3) Graph and off chain computation
The widest path problem is the problem of finding a path between two designated vertices in a weighted graph, maximizing the weight of the minimum-weight edge in the path. (Wikipedia)  

<p align="center">
    <img src="graph.png">
</p>  

In this graph, what is the widest path from E to A and what is its value?  

The widest path from E to A is: E -> D -> C -> B -> A and its value is 31 + 28 + 29 + 25 = 113  


We have a graph with n vertices and m edges (with m>=n). We have multiple parties each having unlimited computational power, but the amount of operations we can do on the blockchain is limited (particularly due to gas cost and gas limit).  

We want to have the value of the widest path between two nodes, but we don’t want to compute it on the blockchain.  
Design a mechanism to have the widest path and its value on the blockchain while maintaining on chain computation cost as low as possible.  
We will assume there is at least one honest party which wants the result to be the widest path (but don’t assume the chain knows who is this honest party).  

I do not know  


What is the computational complexity on chain (for 1 party)?  

I do not know  


## 4) Game theory
Name a strictly positive number. If you name the number which is the most named by all the candidates you succeed in this question.  

- My answer is 1, because this is the smallest integer greater than 0
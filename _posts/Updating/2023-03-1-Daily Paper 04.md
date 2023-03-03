---
layout: post
title: Daily Paper (2023.3.1 - 2023.3.31)
categories: [Updating]
description: Some interesting papers
keywords: 
---

### [31_Learning to Retain while Acquiring: Combating Distribution-Shift in Adversarial Data-Free Knowledge Distillation](https://arxiv.org/pdf/2111.06377.pdf)

- This paper proposes the method called **Learning to Retain while Acquiring**. This method treats the task of Knowledge-Acquisition (learning from newly generated samples) and Knowledge-Retention (retaining knowledge on previously met samples) as meta-train and meta-test, respectively. The propose is to maintain student's performance while updating the generator in the training of Data-free Knowledge Distillation (DFKD). The student update strategies are shown below. It is obvious how the proposes strategy treats the knowledge-acquisition loss and knowledge-retention loss as meta-train and meta-test. The separate strategy is much more helpful for maintain the performance.

![Student Update Strategies](/images/DailyPaper/04/01.png "Student Update Strategies")

- The proposed DFKD is shown below. The structure is similar with the student update strategy shown above. This method may be considered as a kind of attacking strategy as mentioned in the paper because of the meta-train and meta-test. But this strategy can guarantee the performance of student network. This is a kind of trade-off.

![Framework of DFKD](/images/DailyPaper/04/00.png "Framework of DFKD")

### [32_GIVL: Improving Geographical Inclusively of Vision-Language Models with Pre-Training Methods](https://arxiv.org/abs/2301.01893)

- This paper proposes **Geographically Inclusive Vision-and-Language Pre-trained model (GIVL)** to eliminate the cultural difference existed in the culture spread. Besides, **Image-Knowledge Matching (IKM) and Image Edit Checking (IEC)** are designed to pre-train GIVL. IKM is used to learn the alignment between images and corresponding textual knowledge in Wikipedia. IEC is proposed to identify whether a visual concept in input image is replaced by another concept that is visually similar but lies in an irrelevant category.

- IKM is a 3-way classification task: k matches input image I; k mismatches input image I and the visual concept described by k does not fall into a similar category of the visual concept $p_v$ in I; k mismatches input image I but the visual concept described by k falls into a similar category of the visual concept $p_v$ in I. Loss of IKM is a cross-entropy: $L_{IKM} = -\frac{1}{\|D\|}\sum_{i=1}^{\|D\|} log p(y_i^k\|c,k,t,v)$.

- IEC has two types: Input image I remains the same; The visual embedding of the visual concept $p_v$ in input image I is replaced with the embedding of another concept that is visually similar but falls into an irrelevant category with $p_v$. The loss of LEC is $L_{LEC} = -\frac{1}{\|D\|} \sum_{i=1}^{\|D\|}$. The total loss is described as L = $L_{MLM} + L_{ITM} + L_{IKM} + L_{IEC}$. $L_{MLM(Masked Language Modeling)}$ is a loss that describes the average of all cross-entropy loss with respect to the p of predicting the correct masked tokens given a vocabulary. $L_{ITM(Image-Text Matching)}$ enables GIVL to learn the alignment between texts and images. The diagram of GIVL is shown below. This model can actually help the world's culture communicate more efficient and close.

![Framework of GIVL](/images/DailyPaper/04/02.jpeg "Framework of GIVL")

### [33_Network Function Virtualization: State-of-the-Art and Research Challenges](http://ieeexplore.ieee.org/document/7243304/)

- This paper is for the course quiz. This paper introduces **Network Function Virtualization (NFV)**. I will elaborate this paper from NFV and its relationship with complementary fields of software defined networking (SDN) and cloud computing, promising research directions, key NFV projects, standardization efforts, early implementations, use cases, and commercial products. Higher requirements of service provision pushes TSP to develop, and this brings the high cost. If blindly increases the cost, the customers will lost. Therefore, TSPs need to find ways of building more dynamic and service-aware networks. NFV uses the method of leveraging virtualization technology to offer a new way to design, deploy and manage networking services to address these challenges. The main idea of NFV is the decoupling of physical network equipment from the functions that run on them. This allows for the consolidation of many network equipment types onto high volume servers, switches and storage, which could be located in data centers, distributed network nodes and at end user premises. Then Virtual Network Functions(VNFs) can be separated and implemented in the different servers. NFV promises TSPs with more flexibility to further open up their network capabilities and services to users and other services, and the ability to deploy or support new network services faster and cheaper so as to realize better service agility. NFV paves the way to a number of differences in the way network service provisioning is realized in comparison to current practice. (1) Decoupling software from hardware; (2)Flexible network function deployment; (3)Dynamic scaling. Problems contain realization of some of these goals and whether implementation translates to the benefits initially expected. The NFV Architecture is composed of three key elements: Network Function Virtualization Infrastructure (NFVI), VNFs and NFV MANO.

- NFV and Its Relationship with Complementary Fields of Software Defined Networking (SDN) and Cloud Computing:

- Promising Research Directions: (1) With regard to scope, the important aspects of NFV are not considered, such as its relationship with SDN and cloud computing; (2) Limited review and analysis of standardization activities; (3) Incomplete descriptions of ongoing research and state-of-the-art efforts and research challenges.

- Key NFV Projects: (1) Network Architecture and Performance; (2) Security and Resilience; (3) Reliability and Availability; (4) Support for Heterogeneity; (5) Legacy Support; (6) Network Scalability and Automation.

- Standardization:

- Early Implementations:

- Use Cases: Customer Premises Equipment (CPE) in Two Structures; Evolved Packet Core in Two Structures

- Commercial Products: Infrastructure Provider (InP); Telecommunications Service Provider (TSP); VNF Providers (VNFPs) and Server Providers (SPs); Brokers; End Users.

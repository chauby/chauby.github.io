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
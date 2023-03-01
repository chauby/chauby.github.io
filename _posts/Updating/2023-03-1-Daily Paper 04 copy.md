---
layout: post
title: Daily Paper (2023.3.1 - 2023.3.31)
categories: [Updating]
description: Some interesting papers
keywords: 
---

### [31_Learning to Retain while Acquiring: Combating Distribution-Shift in Adversarial Data-Free Knowledge Distillation](https://arxiv.org/pdf/2111.06377.pdf)

- This paper proposes the method called **Learning to Retain while Acquiring**. This method treats the task of Knowledge-Acquisition (learning from newly generated samples) and Knowledge-Retention (retaining knowledge on previously met samples) as meta-train and meta-test, respectively. The propose is to maintain student's performance while updating the generator in the training of Data-free Knowledge Distillation (DFKD).

![Framework of DFKD](/images/DailyPaper/04/00.png "Framework of DFKD")
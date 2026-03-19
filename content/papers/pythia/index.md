---
title: "Pythia: A Suite for Analyzing Large Language Models Across Training and Scaling"
date: 2023-04-03
tags: ["large language models","interpretability","scaling","training dynamics","open source"]
author: ["Stella Biderman", "Hailey Schoelkopf", "Quentin Anthony", "Herbie Bradley", "Kyle O'Brien", "Eric Hallahan", "Mohammad Aflah Khan", "Shivanshu Mishra", "Shivangee Prashanth", "Lintang Sutawika", "Eduard Beeching", "Teven Le Scao", "Leandro Von Werra", "Aviya Skowron"]
description: "Pythia is a suite of 16 LLMs trained on public data in the same order, enabling controlled study of training dynamics and scaling behavior."
summary: "Pythia is a suite of 16 large language models trained on public data in the same order, enabling reproducible and controlled study of how LLMs behave during training and at scale."
cover:
    image: "pythia.png"
    alt: "Pythia model suite overview"
    relative: true
editPost:
    URL: "https://arxiv.org/abs/2304.01373"
    Text: "ICML 2023"
---

---

##### Download

+ [Paper](https://arxiv.org/pdf/2304.01373)
+ [Code and models](https://github.com/EleutherAI/pythia)

---

##### Abstract

How do large language models (LLMs) develop and evolve over the course of training? How do these patterns change as models scale? To answer these questions, we introduce Pythia, a suite of 16 LLMs all trained on public data seen in the same order and ranging in size from 70M to 12B parameters. We provide public access to 154 checkpoints for each one of the 16 models, alongside tools to download and reconstruct their exact training dataloaders for further study. We intend Pythia to facilitate research in many areas, and we present several case studies including novel results in memorization, term frequency effects on few-shot performance, and gender bias. We demonstrate that this highly controlled setup can be used to make novel insights toward LLMs and their training dynamics. Trained models, analysis code, training code, and training data can be found at https://github.com/EleutherAI/pythia.

---

##### Citation

Biderman, Stella, Hailey Schoelkopf, Quentin Anthony, Herbie Bradley, Kyle O'Brien, Eric Hallahan, Mohammad Aflah Khan, Shivanshu Mishra, Shivangee Prashanth, Lintang Sutawika, Eduard Beeching, Teven Le Scao, Leandro Von Werra, and Aviya Skowron. 2023. "Pythia: A Suite for Analyzing Large Language Models Across Training and Scaling." *ICML 2023*. https://arxiv.org/abs/2304.01373.

```BibTeX
@inproceedings{biderman2023pythia,
  title={Pythia: A suite for analyzing large language models across training and scaling},
  author={Biderman, Stella and Schoelkopf, Hailey and Anthony, Quentin Gregory and Bradley, Herbie and O'Brien, Kyle and Hallahan, Eric and Khan, Mohammad Aflah and Mishra, Shivanshu and Prashanth, Shivangee and Sutawika, Lintang and others},
  booktitle={International Conference on Machine Learning},
  pages={2397--2430},
  year={2023},
  organization={PMLR}
}
```

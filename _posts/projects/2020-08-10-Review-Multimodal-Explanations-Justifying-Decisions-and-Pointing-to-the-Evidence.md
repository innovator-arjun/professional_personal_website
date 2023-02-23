---
layout: post
title:  "Multimodal Explanations: Justifying Decisions and Pointing to the Evidence"
description: ""
date:   2023-02-23
type: card-img-top
categories: latin text
image: /assets/img/posts/cr_show_attend_tell.png # for local images, place in /assets/img/posts/
caption:
last-updated: 2023-02-23
categories: Paper Review
tag: Paper Review
author: Arjun Vaithilingam Sudhakar
card: card-1
---
<!-- ![key image](/assets/img/posts/cr_show_attend_tell.png) -->
<a href="url"><img src="/assets/img/posts/cr_show_attend_tell.png" align="center" height="350" width="750" ></a>

Paper Link --> [Multimodal Explanations: Justifying Decisions and Pointing to the Evidence](https://openaccess.thecvf.com/content_cvpr_2018/papers/Park_Multimodal_Explanations_Justifying_CVPR_2018_paper.pdf)
## Summary:

Understanding the factors that influence the decision-making process of machine learning models is essential for their interpretability. In this paper, the authors present two contributions. Firstly, they introduce two datasets, namely ACT-X and VQA-X, which provide visual and textual explanations for classification decisions. Current datasets lack access to explanations for a decision in the current datasets. Secondly, they propose a novel multimodal Pointing and Justification Explanation (PJ-X), enabling the model to visually indicate the evidence supporting its decision and justify it with text. 

Previous methods were limited in providing explanations in only one modality, i.e., unimodal explanation. They could either explain through text conditioned on the image or use only images to visualize the model attending. Addressing this problem, the proposed PJ-X system provides the model's prediction using an attention mask to identify the salient region without using domain knowledge. Overall, this paper presents a major advance in the field of explainability and sets the stage for further research in this area through novel datasets and architecture.

## Strong Points:
- Added textual and visual explanations in the visual question answering and activity recognition dataset to evaluate how the model-generated answers correspond to the humans. 
- Introducing a multimodal system that can make predictions, provide natural language justifications for decisions, and accurately point to the relevant supporting part in an image.
- Finally, this paper concludes by conducting an extensive analysis of the insights gained from the proposed multimodal explanation approach and contrasting it with the unimodal explanation approach. Additionally, ablation studies were performed to evaluate the effectiveness of descriptions versus explanations. 

## Weak Points:
- Based on the constraints implied during the collections, answers and textual explanations hinders the open form, which is most practical in real application. EG: Most of the sample images provided in this paper start with because. Will the performance drop if there is a variation in the explanations generated?
- When comparing the VQA-X dataset with VQA, it has a significantly smaller training set. As collecting explanations is a harder and more expensive process.
- Very little to no ablations were done on the architecture to understand the effects of the components in the overall system. Regarding network parameters, choice of normalizations, run time vs. model size and accuracy improvements tradeoff, etc.


## Reflections:
- Understanding the effect of bias in the VQA systems compared to VQA-X. Using explanation information, can we make the model learn non-spurious correlation? I.e., forcing the model to focus on the information perceived the humans to make it less biased.
- Since the dataset collection process is expensive, transferring this approach to other systems is challenging. Hence using some self-supervised approach or data-efficient adaptions can help the system to improve its performance and provide faithful explanations.


## Most interesting thought: 
Recent work in self-supervised transformer architecture, like VisualBert, and ViLBERT, has pushed the boundaries in Vision-Language systems. It would be interesting to use transformer modules in this system to evaluate the model regarding explanations and performance as they are trained. 

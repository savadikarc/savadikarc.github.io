---
title: "GIFT: Generative Interpretable Fine-Tuning"
link: https://arxiv.org/abs/2312.00700
venue: Preprint
thumbnail: gift.svg
authors: 
    - name: "<b>Chinmay Savadikar</b>"
    - name: "Xi Song"
    - name: "Tianfu Wu"
      url: https://ece.ncsu.edu/people/twu19/
pdf: https://arxiv.org/pdf/2312.00700.pdf
code: https://github.com/savadikarc/gift
web: https://savadikarc.github.io/gift/
description: GIFT is a method for parameter efficient fine-tuning of pretrained Transformer models with built-in interpretability. GIFT generates the fine-tuning residual weights \(\Delta\omega\) directly from the pretrained weights, and is shared across all the layers of the pretrained transformer selected for fine-tuning. Simply parameterizing GIFT with two plain linear layers (without bias terms) is surprisingly effective, i.e., \(\hat{\omega}=\omega \cdot (\mathbb{I}+\phi_{d_{in}\times r}\cdot \psi_{r\times d_{in}})\). On image classification tasks, the output of the first linear layer in GIFT plays the role of a \(r\)-way segmentation head without being explicitly trained to do so.
date: 2023-12-01
---

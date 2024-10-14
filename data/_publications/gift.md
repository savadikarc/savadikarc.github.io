---
title: "GIFT: Generative Parameter-Efficient Fine-Tuning"
link: https://arxiv.org/abs/2312.00700
venue: Preprint
thumbnail: gift.svg
thumbnail_alt: gift-alt.svg
authors: 
    - name: "<b>Chinmay Savadikar</b>"
    - name: "Xi Song"
    - name: "Tianfu Wu"
      url: https://ece.ncsu.edu/people/twu19/
pdf: https://arxiv.org/pdf/2312.00700.pdf
code: https://github.com/savadikarc/gift
web: https://savadikarc.github.io/gift/
description: GIFT induces an explicit and direct mapping between the fine-tuned model and the frozen pretrained model, i.e., learns the fine-tuned weights directly from the pretrained weights. We show that the finetuned weights can be learned using a simple linear transformation of the pretrained weights, \(\hat{\omega}=\omega \cdot (\mathbb{I}+\phi_{d_{in}\times r}\cdot \psi_{r\times d_{in}})\), where trainable parameters \(\phi_{d_{in}\times r}\) and \( \psi_{r\times d_{in}}\) are shared across all the pretrained layers. GIFT outperforms prior methods on multiple Natural Language benchmarks using Llama series of models. On image classification tasks, the output of the first linear layer in GIFT plays the role of a \(r\)-way segmentation head without being explicitly trained to do so.
date: 2023-12-01
---

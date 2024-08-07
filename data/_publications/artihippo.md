---
title: "Transforming Transformers for Resilient Lifelong Learning"
link: https://arxiv.org/abs/2303.08250
venue: Preprint
thumbnail: artihippo.svg
authors: 
    - name: "<b>Chinmay Savadikar</b>"
    - name: "Michelle Dai"
    - name: "Tianfu Wu"
      url: https://ece.ncsu.edu/people/twu19/
pdf: https://arxiv.org/pdf/2303.08250.pdf
description: We present a method to add lightweight, learnable parameters to Vision Transformers while leveraging parameter-heavy, but stable components. We show that the final linear projection layer in the multi-head self-attention (MHSA) block can be used as this light-weight module using a Mixture of Experts framework. While most of the prior methods which address this problem induce learnable parameters at every layer, or heuristically choose where to do so, we use Neural Architecture Search to determine this automatically. We use SPOS Neural Architecture Search and propose a task-similarity oriented sampling strategy to replace the uniform sampling and achieve better performance and efficiency than uniform sampling.
date: 2023-03-23
---

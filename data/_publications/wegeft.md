---
title: "WeGeFT: Weight‑Generative Fine‑Tuning for Multi‑Faceted Efficient Adaptation of Large Models"
link: https://openreview.net/forum?id=K0sv5T2usb
venue: ICML 2025
thumbnail: wegeft.svg
authors: 
    - name: "<b>Chinmay Savadikar</b>"
    - name: "Xi Song"
    - name: "Tianfu Wu"
      url: https://ece.ncsu.edu/people/twu19/
pdf: https://openreview.net/pdf?id=K0sv5T2usb
code: https://github.com/savadikarc/wegeft
web: https://savadikarc.github.io/wegeft/
description: While LoRA inherently balances parameter, compute, and memory efficiency, many subsequent variants trade off compute and memory efficiency and/or performance to further reduce fine-tuning parameters. WeGeFT addresses this limitation, unifies PEFT and ReFT, and reduces the parameter count while maintaining performance by generating the fine-tuning weights directly from the pretrained weights. WeGeFT employs a simple low-rank formulation consisting of two linear layers, either shared across multiple layers of the pretrained model or individually learned for different layers.
order: 2
---

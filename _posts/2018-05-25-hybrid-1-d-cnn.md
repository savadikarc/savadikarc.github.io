---
layout: post
title: "Hybrid 1-Dimensional Convolutional Neural Network"
date: 2018-04-25
comments: true
author: "Chinmay Savadikar"
categories: post
summary: true
tldr: A description of a component my BE Project.
thumbnail: "conv_filter.gif"
---

<link href="/assets/hybrid/style.css" rel="stylesheet">

So for the past few months, I've been working on my Final Year Undergraduate project - "DeepSense: Deep Learning based Music Emotion Recognition".
As the name suggests, the goal of the project is to recognize emotions in music, using Deep Learning. For this purpose, we're (me, and my 2 project partners, who are not on GitHub),
are using a stacked architecture of a Hybrid 1-Dimensional Convolutional Neural Network (CNN, ConvNet), and an Long-Short Term Memory (LSTM). We will call this as the *model*.
The purpose of this post is to explain the [***Hybrid 1-Dimensional CNN***](#hybrid-1-dimensional-cnn), which is really just a ***small*** modification of 2-Dimensional CNN. A big advantage of
CNNs is that they employ parameter sharing, and thus reduce the number of parameters by a great number. This also adds an inherent regularization effect. In case you are already familiar with 2-D and 1-D CNNs, feel free to click on the link and head over to Hybrid 1-Dimensional CNN section.

### Input
We use Mel-Frequency Cepstral Coefficients as the input to the model, which represent the amplitudes of frequencies at various time instances. It is an array where rows represent time segments, and each column represents a frequency. Hence we get a two dimensional array, which can be interpreted as a sequence of frequency components. 
Now that we know what our input is, let us first discuss how 2-D and 1-D CNNs work (this will show why we call our CNN as *hybrid*).
 
### 2-Dimensional CNN
CNNs are meant to operate on spatial data. Audio signals vary spatially in one dimension (time), Images vary in 2 dimensions, and Videos vary in 3 dimensions. A 2-dimensional CNN is used for operating on images. I will write a separate detailed post, but I'd recommend watching the [cs231n](http://cs231n.stanford.edu/) [lecture on CNNs](https://youtu.be/bNb2fEVKeEo?list=PL3FW7Lu3i5JvHM8ljYj-zLfQRF3EO8sYv). Figure 1 illustrates this operation.

<div class="row md-img-container">
	<div class="col md-imgs">
		<div class="row">
			<img class="img-fluid" src="/assets/hybrid/2D_cnn1.png">
		</div>
		<div class="row">
			<p><b><i>Figure 1</i>:</b> The dot product of the input (red) and the filter (green) produces an activation map of size <b>N' X M' X F</b> where F is the number of filters.</p>
		</div>
	</div>
</div>

### 1-Dimensional CNN
In Natural Language Processing, the input is a sentence. The words are typically converted into dense, lower dimensional representation called word embeddings.
Let this representation be of *N* dimensions, and the number of words in a sentence be *T*. Hence, the sentence will now be represented as a ***T X N*** array. In a 1-Dimensional
CNN, the filter size is set to ***T' X N***, where ***T'*** is the number of timesteps we want to span. Figure 2 illustrates this.

<div class="row md-img-container">
	<div class="col md-imgs">
		<div class="row">
			<img class="img-fluid" src="/assets/hybrid/1d_cnn.jpg">
		</div>
		<div class="row">
			<p><b><i>Figure 2</i>:</b> The dot product works the same as a 2-D CNN, except we only slide the filter in the time-axis.</p>
		</div>
	</div>
</div>


### Hybrid 1-Dimensional CNN
Now let's say we apply both types on CNNs to the input we introduced earlier. Remember, rows represent time segments, and each row contains a feature vector.
If we apply any of the 2 types of CNNs to our input, the output will be a function of current, past and future time segments. This is very unintuitive in context of music.
When we listen to music, we have no knowledge of the time segments to come (at least when we are listening to it for the first time). Thus, the intuition was that these
time segments must interact in a very structured way. We fixed the number of rows in the filter to 1, as opposed to an arbitrary number in 1-D CNN. Hence, the CNN is processing just one time segment at a time.
The intuition behind a 2-D filter as applied to an image is that a certain filter "looks" for a certain feature in the image. To replicate this, we set the filter size to be small, and slide it over the input feature vector.
The CNN filters are now looking for certain features in each time segments, independent of other time segments. The time segments interact with each other due to the LSTM, which is stacked over the CNN. Hence, we are processing the input sequentially.

<div class="row md-img-container">
	<div class="col md-imgs">
		<div class="row">
			<img class="img-fluid" src="/assets/hybrid/hybrid_1D_cnn.png">
		</div>
		<div class="row">
			<p><b><i>Figure 3</i>:</b> Hybrid 1-Dimensional CNN. The figure shows just the first 6 steps, but the same operation repeats over the entire input.</p>
		</div>
	</div>
</div>

### References
1. Malik, M., Advanne, S., Drossos, K., Virtanen, T., Ticha, D. and Jarina, R. (2017) Stacked Convolutional and Recurrent Neural Networks for Music Emotion Recognition. Proceedings of the 14th Sound and Music Computing Conference, July 5-8, Espoo, Finland.
2. Andrej Karpathy, Stanford University, Dept. of Computer Science, "Connecting Images and Natural Language", [http://purl.stanford.edu/wf528qt3314](http://purl.stanford.edu/wf528qt3314)
3. On word embeddings - Part 1: [http://ruder.io/word-embeddings-1/](http://ruder.io/word-embeddings-1/)

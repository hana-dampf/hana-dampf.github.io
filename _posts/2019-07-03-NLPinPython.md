---
layout: post
title: "Pablo Neural-da: I learn Python, my model learns what love is"
categories: [Python, Machine Learning, Language]
---

##Under Construction!

So, how am I spending my free time these days? Very slowly learning Python. Working with natural language processing seemed like a good way to stay humble.

I did this using the [Beautiful Soup library](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) for webscraping, and based my approach on Zach Thoutt's [LSTM model](https://github.com/zackthoutt/got-book-6), rewriting his tensorflow 1.0.0 RNN in keras, with some changes to the embedding structure.

I decided to train my model on a corpus of Pablo Neruda's model because A) I thought of the Neural-da joke and B) it was very easy to webscrape. I was curious about how well a model trained from nothing, using only my corpus, would do at prediction. These are the results I got using entirely Zach Thoutt's code:

<details open>
<summary>After 200 training epochs</summary>
<br>
Blah Blah
</details>

That's the minimum benchmark I'm trying to hit. You can see after 200 epochs, it's picked up some basic grammar and punctuation structure, which is pretty impressive. But I'm not here to copy-paste someone else's code!

Here's my best results:


<details open>
<summary>After 200 training epochs</summary>
<br>
Blah Blah
</details>

<details open>
<summary>After 400 training epochs</summary>
<br>
Blah Blah
</details>

My current model was built by first translating the entire text corpus into integers, then training my neural net with sequences of integers in 5 batches. The model takes the sequences through an embedding layer (meant to translate each word into a vector encoded by its relationship with other words) where the weights of the embedding are trained with the model (rather than using an existing trained embedding such as Word2Vec). Next, the embedding vector is passed through 3 LSTM layers returning full sequences (dropout 0.3), then passed to a final Dense prediction layer (with softmax activation). This structure returns the probability for all words in the library being the next word after the input (the outputs were the next words after the sequence coded as 1-hot vectors). 

The way poems were generated was the clever idea I borrowed from Zach Thoutt: to make sure the model could take dynamic-length sequences, meaning I could start a poem from a single seed word then use the model's output probabilities to pick each word, then repeat with the 2 word sequence, and so on. Using the model's output probabilities with the np.random.choice function instead of picking the most likely option injected a degree of randomness (meaning it would not recreate exact passages).

If anyone has some suggestions about how to improve this, let me know! 


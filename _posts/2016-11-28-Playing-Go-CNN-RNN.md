---
layout: post
title: Playing GO as I build a Convolution Neural Network and Recurrent Neural Network
---

In the recent months I have been delving into the relm of deep learning. During the course of my work I have had the opportunity
to work on a myriad of projects on which I have successfully implemented networks including but not limited to CNN, bidirectional RNN,
Deconvonets, RCNN, FCN etc. Utilizing my knowledge and driven by curiosity I wondered if I taught something to a CNN and an RNN which
one would perform better? In my quest to find something that could easily be represented by both network I was brought back to a
game I used to play a lot in my undergraduate years on the KGS servers, GO.

You can read more about GO [here](https://en.wikipedia.org/wiki/Go_(game)). Why GO? simply because GO is a game that depends a lot on 
patterns. I have discoverd that instead of reasoning why I place a stone in a particular location often I would play
a move based on intuition and looking at the structures of the stones on the board. Ofcourse I am personally nowhere near good enough
at go to claim my intuition is right or that I am in any way an expert at GO. Instead insights given by professional players often account 
the the high weight of intuition based on recognizing patterns that they have leaned to identify from years of practice in their plays. On the flip side there
is also a certain logic to GO. One cannot play the game of GO simply based on pattern recognition.

Now you may ask where do CNN and RNN come into the picture? Convolutional neural networks(CNN) are displaying amazing results in image
classification(CIFAR, MINST etc.), face recognition and many other tasks. Based on our reasoning that intuition plays a major role
in the decision making of the player it stands to reason that CNN would be our first choice to predict the best possible move for a given
state of the game. Now the fun question, why train an RNN? well simply put no reason at all apart from curiosity. I read this [blog post](http://karpathy.github.io/2015/05/21/rnn-effectiveness/)
that portrayed amazing things that could be achieved using RNNs and it got me wondering what would happen if I had the RNN try and
predict the best possible move for the current state of the game if I provided it the state of the game from beginning till the end.
Like words in a sentence that have a logical relationship do moves in GO have one too? Can the RNN similar to how it learns to write english
from scrath in the blog learn to play GO too? I will find out.

To begin with I will explore a CNN network a preliminary version of which is available on my [github](https://github.com/aditya-rajagopal/gorc).
This repository includes a script to read sgf files(which are a standard format of game annotations) and parse it into board-move pairs to 
be used for training. Secondly, it contains a basic CNN written in Tensorflow with the corresponding batching script. This CNN is being 
tuned locally and will be updated with results and a detailed explaination. I am currently in the process of writing the RNN and that too
will be shortly updated.

I dont expect to make any ground breaking discoveries this is merely satiating my curiosity, mostly towards how effective RNNs will
be for learning to play GO. There have already been many papers describing GO predictors based on CNN however I would still like to
work my way up designing a network from scratch more as a learning experience than anything else.

####An indication of what kind of network I am currently going for.
I am currently using a 9 convolution and 2 FC layer network which is giving around a 46% accuracy on the testing set of 10 games with over 96% on training of about 100 games( clearly not an indication of anything I mainly used it to test out the proper functioning of the network). More on this later.

![Example of CNN network I am currently using as of the latest commit](../images/cnn_graph.png? raw=true "Current CNN model")

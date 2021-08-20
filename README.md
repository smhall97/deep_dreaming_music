# Deep Dreaming Music
***Neuromatch Academy Deep Learning 2021 project by [Maryam Faramarzi](https://github.com/MaryamFaramarzi), [Siobhan Hall](https://github.com/smhall97), [Máté Mohácsi](https://github.com/mohacsimate), [Pablo Oyarzo](https://github.com/oyarzou), [Jonathan Reus](https://github.com/jreus) and [Katherine Baquero](https://github.com/KatherineBaq)***

*Special credit to our TAs: [Pedro F da Costa](https://github.com/PedroFerreiradaCosta) and [Beatrix BenkÅ](https://github.com/bbeatrix)*

---

## Background
During the last decade CNNs have become increasingly powerful as models for computer vision. Their development has been carried conjointly with the exploration of their internal informational structure (1) and feature-inference processes. One of these approaches known as “dreaming”, initially developed by Google (2), has proven to be an effective method to maximize features and to take convolutional neural networks to the territory of stimuli generation. 
In this work, we ask how audible waveforms can be reconstructed from features by exploring dreaming algorithms as a method. This method has the capacity to work as an introspective technique for understanding internal network representations, as well as potentially acting as a generative approach for novel audio output. 
CNNs have been used to achieve state-of-the-art performance classifying music genres from (Mel Scale) spectrograms (3), thus we choose to explore the problem of music genre classification as a starting point for exploring internal representations. While most literature on CNN-based music genre classifiers use Mel-scale Spectrograms, this audio representation can be potentially limiting in the specific situation of deep dreaming on spectrograms, where the end goal is to reconstruct an audible time-domain waveform. It is for this reason we investigated the following audio transforms: Short-Time-Fourier Transforms (STFTs) and Mel-spectrograms. These will be collectively referred to as Spectrograms throughout.


## Aims
- To determine if audible waveforms can be reconstructed using the "dreaming" process from features learned by a convolutional neural network. 
- To investigate the best approach to training a classifier as well as choosing the type of audio data transform that can be reconverted to music once “dreamed” upon. 

## Methods
![Overall pipeline - from classification to dreaming](https://github.com/smhall97/deep_dreaming_music/blob/main/Pipelines/Overall%20pipeline.png)


## Findings
### Audio Reconstruction after dreaming
In applying the dreaming to the spectrograms, we gain insight into the learned representations the model uses to perform the classification. We are able to visually represent these features, as well as interpret them in audio formats. 

We were limited by our audio reconstruction techniques which immediately revealed a catch-22.

We were able to achieve high classification accuracies when training the models with Mel-spectrograms, but these cannot be cleanly reconverted to audio data.
While STFTs are cleanly converted to audio (without noise added during reconstruction), we achieved lower classification accuracies when training with STFTs. This poor classification accuracy suggests the model didn’t learn useful internal representations that can be maximised during the dreaming process that will transform an input while obeying the laws of spectrograms to ensure it can be reconstructed into audio. 

### Future directions

The focus on only visual representations of the audio data limited our results as we were limited by audio reconstruction techniques. Future work could investigate using the raw audio signal and using models better suited to signal data (e.g. RNNs, Transformers or autoregressive models such as WaveNet). This limitation was further evident in our use of networks pre-trained on ImageNet alone. Future work could incorporate pre-training on more applicable data such as STFT transforms to help the model learn better internal representations to be maximised during dreaming.  


## References
1. Olah C, Mordvintsev A, Schubert L. Feature visualization. Distill. 2017 Nov 7;2(11).
2. 	Google AI Blog: Inceptionism: Going Deeper into Neural Networks [Internet]. [cited 2021 Aug 16]. Available from: https://ai.googleblog.com/2015/06/inceptionism-going-deeper-into-neural.html
3. 	Palanisamy K, Singhania D, Yao A. Rethinking CNN Models for Audio Classification. arXiv. 2020 Jul 22;
4. 	Simonyan K, Zisserman A. Very deep convolutional networks for large-scale image recognition. arXiv preprint arXiv:14091556. 2014; 





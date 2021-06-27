---
layout: page
title: Music genre classifier
description: Deep learning models for music classification
img: /assets/img/mel.png
importance: 3
category: University
---

Different architectures to classify music files based on genre from the GTZAN music corpus, namely:

* Convolutional Neural Network (CNN)
* Recurrant Neural Network (RNN)
* Inception V3
* MobileNet V2


(Implementated with Tensorflow)

### Dataset 


In the GTZAN music corpus there's 10 genres with 100 songs each (1000 in total): 80% of it was used during the training phase (800 images), and 20% for testing (200 images). After the split, each song of 30 seconds is split in chunks of 10 seconds (resulting in 2400 and 600 training and testing samples).

Dataset can be downlaoded here: http://marsyas.info/downloads/datasets.html


### Audio augmentation 

To increase further the amount of data, some augmentation were done on the audio files. For each song chunk, we applied:

* Add light random noise in the wave form
* Add intense random noise in the wave form
* Increase randomly pitch (2% at most)


### Audio features extracted


For exctracting the audio features, the library librosa was used.

Mel-frequency spectrogram as images of size 512x512 (in black and white)

Combination of Mel-frequency spectogram, spectral centroid and spectral contrast stacked as images of size 512x512



</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/spectro.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Example of Mel-frequency Spectrograms
</div>



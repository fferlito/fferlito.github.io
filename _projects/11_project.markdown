---
layout: page
title: Detecting Machine Translated Text using BERT
description: using the Opensubtitles corpus
img: /assets/img/bert.jpeg
importance: 4
category: NLP
---

Machine translation has seen massive improvements over recent years. Especially supervised models are coming ever closer to human parity. Free tools like Google Translate or Deepl allow people to achieve these levels of translations easily, without requiring a human expert. This raises concerns due to the ease of translating and spreading things like 'fake news'. 

In contrast to corpora in machine translation that often use crawled news like WMT2014, the novel idea of using subtitles is presented. In this project, translated subtitle sentences are classified to find out if they are human or machine translated. Subtitles taken from the Opensubtitles corpus are translated from Italian to English and Dutch to English. BERT-models of different sizes are fine-tuned for this classification task on the respective language directions.

Results indicate that classification was more successful for the Dutch to English direction compared to the Italian to English, with some improvements seen in larger BERT models. Nevertheless, the paper presents a promising and novel direction in machine translation classification, with several ideas for future explorations. 

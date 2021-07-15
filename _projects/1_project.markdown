---
layout: page
title: Decoding the Dead Sea Scrolls with Deep learning
description: An analysis including line segmentation, character segmention and classification of the type of scroll
img: /assets/img/dss.jpeg
importance: 1
category: deep learning
---

The field of Optical Character Recognition (OCR) has made big improvements over the last years , yielding very high recognition rates, especially when dealing with handwritten characters. This analysis allows to convert typed and handwritten characters into digital format, so that they can be stored electronically and further analyzed on a computer.  However, this still poses some problems, since there is a big variability in the style, both between different writers, and within the same writer.

The task of character recognition becomes more challenging when dealing with historical handwritten documents. The field where these manuscripts are studied is called paleography (a word with Greek roots meaining παλαιός, palaiós, "old", and γράφειν, gráphein, "to write"), which focus on deciphering, reading, and dating historical manuscripts, as well as the understanding of the cultural context of writing. Of particular interest is the dating these manuscripts, which allows to understand the different writing styles of these documents according to the period in which they are written. A traditional way to do this is using a radiocarbon dating analysis, which is a method to figure out the period of an object that contains organic material, using the properties of radiocarbon. This method was used for example to date some parts of the Dead Sea Scrolls.  This is  a  collection  of  ancient  manuscripts  with   historical,  religious,  and linguistic significance. This method yields good results, however it requires a lot of hand labour and knowledge in the field.

In this project, I developed with some course mates a novel approach for style classification of historical documents, applied to the Dead Sea Scrolls (DSS). Using an algorithm to date historical documents offers many advantages, from the speed of running the analysis, to the cost of doing it (doing a carbon analysis requires a chemical laboratory and reagents, which not everybody can access). Most of the texts of the DSS collection use Hebrew, with some written in Aramaic and a few in Greek.  For this analysis, we only use Hebrew characters. The Dead Sea Scrolls collection exhibits writing styles from three different periods: Archaic, Hasmonean, and Herodian. 


In order to understand the style of writing of a scroll, we have to solve two different tasks: the first is the extraction of the characters from the scrolls. Once the characters are obtained, these can be used as features for the style classification, as shown by previous research. The reason of this is that each writer has a different writing style, which varies from the way a character is written, to the angle these characters have compared to the line on the page. 

The first task (the character extraction) can be subdivided in three main tasks: first, the line segmentation, in which each line of a document is extracted; second, the character segmentation, which allows to extract the individual characters from the results of the first step; lastly, the character recognition, that allows us to store the scrolls into digital format.

    ---
    layout: page
    title: project
    description: a project with a background image
    img: /assets/img/12.jpg
    ---

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/line.jpg' | relative_url }}" alt="" title="Example of line segmentation"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/char_seg_result.png' | relative_url }}" alt="" title="Example of character segmentation"/>
    </div>
</div>
<div class="caption">
    Caption photos easily.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
```

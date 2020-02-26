# Segmentation Evaluation after border thinning
## Python implementation of [Rand error and Variation of Information](https://imagej.net/Segmentation_evaluation_after_border_thinning_-_Script)
The following Jupyter Notebook allows you to evaluate the performance of your segmentation method after thinning the borders of the image segments to 1-pixel width.

Retrospective evaluation of the original [ISBI-2012 segmentation challenge](http://brainiac2.mit.edu/isbi_challenge/) scoring system revealed that it was not sufficiently robust to variations in the widths of neurite borders. After evaluating all of these metrics and associated variants, it was found that specially normalized versions of the [Rand error](https://imagej.net/Rand_error) and [Variation of Information](https://imagej.net/Rand_error) best matched our qualitative judgements of segmentation quality:
* Foreground-restricted Rand Scoring after border thinning
* Foreground-restricted Information Theoretic Scoring after border thinning

Further details about the metrics can be found in the [challenge publication](http://journal.frontiersin.org/article/10.3389/fnana.2015.00142/abstract).

## Prerequisties
This code has been implemented in Jupyter. You need to install [pyimagej](https://pypi.org/project/pyimagej/) which is a python wrapper for ImageJ. 

To install pyimagej:
```
$ pip install pyimagej
```
To install scikit-image:
```
$ pip install scikit-image
```
You will also need to install [Fiji](https://imagej.net/Fiji/Downloads). If you have already installed Fiji, then we are good!

## Run
1. This repository includes a folder `Fiji.app` which is imported to access the segmentation metric libraries of ImageJ. If you are interested in importing your installed version of Fiji, change the path in **Line 2** of the code to the desired Fiji.app folder path on your local machine.
2. The Groundtruth and Results (for example segmentation outputs of your network, method, etc.) in this repository are in `.png` format. If the formats of your data are different, change the formats in **Line 3** accordingly.
3. Change the paths of the macros in **Line 4** to the current working directory where this notebook runs in.

# double_periodogram

## The paper 

“[Studies in Astronomical Time Series Analysis: The Double Lomb-Scargle Periodogram and Super Resolution](https://arxiv.org/abs/2601.04552),” by Jeff Scargle and Sarah Wagner, describes the origin and use of multiple-frequency periodograms (which we call omnigrams for bases more general than the sinusoidal one).

This repository contains both code, and symbolic algebra scripts for generating this code, for four flavors of double periodogram — derived by maximizing or marginalizing the Gaussian likelihood, and with or without implementing the Lomb phase shift technique.

### MATLAB:

Two MatLab scripts derive omnigrams using symbolic algebra:
max_like_ommigrams.m 
Currently the maximum likelihood script works only for double periodgrams (4 terms in the time series model), but can be generalized using the same symbolic operations used to make bayesian omnigrams with models with an arbitrary number of terms (tested as far as the triple periodogram).

bayesian_omnigrams


Their output was cut and pasted into the operational scripts:

double_schuster.m                               DSP
double_lsp.m                                        DLSP
double_bretthorst_schuster.m.             DBSP
double_bretthorst_lomb_scargle.m      DBLSP

The demonstration script — test.m — runs all 4 of the double periodogram functions on synthetic data consisting to two sinusoids close in frequency.  The resulting double periodograms are shown as contour plots. The true values of the frequencies of the test sinusoid pair are magenta squares; those of the  maxima of the double periodograms are red dots.


### PYTHON:
TBD

#### Notes: 

All frequencies are in radians per second (2 pi times cycles per second).

The choice of frequencies at which to evaluate the periodograms is completely free, and need not be in the rectangular arrays in the test examples. 

The effective fundamental period to use is a crucial parameter,  especially for super resolution applications.  As implemented in the test scrip, it is recommended that the fundamental frequency (2 pi / time range) be reduced — such as in the test script where it is reduced by a factor “ww_over “ of 50, to be able to resolve features corresponding smaller than indicated by the Rayleigh criterion.

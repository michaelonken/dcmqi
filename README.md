[![Circle CI](https://circleci.com/gh/QIICR/dcmqi.svg?style=svg)](https://circleci.com/gh/QIICR/dcmqi)
[![Build status](https://ci.appveyor.com/api/projects/status/04l87y2j6prboap7?svg=true)](https://ci.appveyor.com/project/fedorov/dcmqi)
[![TravisCI](https://travis-ci.org/QIICR/dcmqi.svg?branch=master)](https://travis-ci.org/QIICR/dcmqi)
[![Docker](https://img.shields.io/docker/automated/qiicr/dcmqi.svg)](https://hub.docker.com/r/qiicr/dcmqi/)
[![OpenHub](https://www.openhub.net/p/dcmqi/widgets/project_thin_badge.gif)](https://www.openhub.net/p/dcmqi)

# Introduction

dcmqi (DICOM (**dcm**) for Quantitative Imaging (**qi**)) is a collection of libraries and command line tools with minimum dependencies to support standardized communication of [quantitative image analysis](http://journals.sagepub.com/doi/pdf/10.1177/0962280214537333) research data using [DICOM standard](https://en.wikipedia.org/wiki/DICOM).

Specifically, the current focus of development for dcmqi is to support conversion of the following data types to and from DICOM:
* voxel-based segmentations using [DICOM Segmentation IOD](http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_A.51.html)
* parametric maps using [DICOM Parametric map IOD](http://dicom.nema.org/medical/dicom/current/output/chtml/part03/sect_A.75.html)
* image-based measurements using [DICOM Structured Reporting (SR) template TID1500](http://dicom.nema.org/medical/dicom/current/output/chtml/part16/chapter_A.html#sect_TID_1500)

As an introduction to the motivation, capabilities and advantages of using the DICOM standard, and the objects mentioned above, you might want to read this open access paper:

> Fedorov A, Clunie D, Ulrich E, Bauer C, Wahle A, Brown B, Onken M, Riesmeier J, Pieper S, Kikinis R, Buatti J, Beichel RR. (2016) DICOM for quantitative imaging biomarker development: a standards based approach to sharing clinical data and structured PET/CT analysis results in head and neck cancer research. *PeerJ* 4:e2057 https://doi.org/10.7717/peerj.2057

dcmqi is developed and maintained by the [QIICR](http://qiicr.org) project.

# Getting started

* installation and usage instructions are available in [dcmqi manual](https://qiicr.gitbooks.io/dcmqi-guide).
* check out our [introductory tutorial](http://qiicr.org/dcmqi-guide/tutorials/intro.html)

# License

dcmqi is distributed under non-restrictive BSD-style license (see full text [here](https://github.com/QIICR/dcmqi/blob/master/LICENSE.txt)) that does not have any constraints on either commercial or academic usage.

Our goal is to support and encourage adoption of the DICOM standard in both academic and research tools. We will be happy to hear about your usage of dcmqi, but you don't have to report back to us.

# Support

You can communicate you feedback, feature requests, comments or problem reports using any of the methods below:
* [submit issue](https://github.com/QIICR/dcmqi/issues/new) on dcmqi bug tracker
* post a question to [dcmqi google
  group](https://groups.google.com/forum/#!forum/dcmqi)
* send email to [Andrey Fedorov](http://fedorov.github.io)
* leave comments in the [dcmqi user guide](https://qiicr.gitbooks.io/dcmqi-guide)

# Acknowledgments

This work is supported in part the National Institutes of Health, National Cancer Institute, [Informatics Technology for Cancer Research (ITCR) program](https://itcr.nci.nih.gov/), grant [Quantitative Image Informatics for Cancer Research (QIICR)](http://qiicr.org) (U24 CA180918, PIs Kikinis and Fedorov).

# References

1. Fedorov A, Clunie D, Ulrich E, Bauer C, Wahle A, Brown B, Onken M, Riesmeier J, Pieper S, Kikinis R, Buatti J, Beichel RR. (2016) DICOM for quantitative imaging biomarker development: a standards based approach to sharing clinical data and structured PET/CT analysis results in head and neck cancer research. *PeerJ* 4:e2057 https://doi.org/10.7717/peerj.2057

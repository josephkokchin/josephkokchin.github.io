---
title: "My Tex setup for academic reports"
subtitle: My personal Tex setup for academic reports.
layout: post
date: 2019-07-11 10:10
tag:
  - LaTex
  - Tex
  - Personal Setup
  - PDF
image: ../assets/posts/IBMBadge.png
headerImage: False
category: blog
author: rodferro
description: My personal Tex setup for academic reports.
---

Several times we want to create amazingly beautiful documents, and in order to do that, we use Tex/LaTex. The thing is that we will find out that most of the time when using an IDE ([Texmaker](http://www.xm1math.net/texmaker/) for instance) it will generate a lot of documents (`.aux`, `.logs`, etc.) that we won't use at the end. Motivated by this, I want to share with you my personal Tex setup to avoid creating all this documents.

First of all, we will need to create the basis, the main document which will be called `report.tex`. The main content I usually use for this is the following:

```tex
% Document class and specifications:
\documentclass[10pt, letterpaper, twoside]{report}

% Packages:
% \usepackage[margin=1.4in]{geometry}
\usepackage[width=150mm, top=25mm, bottom=25mm, bindingoffset=6mm]{geometry}
\usepackage[utf8]{inputenc}
\usepackage[english]{babel}
\usepackage{enumerate}
\usepackage{amsmath}
\usepackage{fancyhdr}
\pagestyle{fancy}

% Graphics:
\usepackage{graphicx}
\usepackage[usenames, dvipsnames]{color}
\graphicspath{ {imgs/} }

% Tabular:
\usepackage{booktabs}
\renewcommand{\arraystretch}{2}
% \setlength{\arrayrulewidth}{0.25mm}

% Citation:
\usepackage[natbibapa]{apacite}
\bibliographystyle{apacite}

% Meta (Fira Sans):
% \usepackage[sfdefault]{FiraSans}
% \setmainfont{Fira Sans}
% \setsansfont{Helvetica}
% \setmonofont{Menlo}

% Meta (Lato):
\usepackage{fontspec}
\setmainfont{Lato Light}
\setsansfont{Fira Sans}
% \setmonofont{Space Mono}[Scale=0.8]
\setmonofont{Hack}[Scale=0.8]

% Minted:
\usepackage[outputdir=.latex-cache]{minted}
% Color references:
% https://www.sharelatex.com/learn/Code_Highlighting_with_minted#Reference_guide
\usemintedstyle{rainbow_dash}
\renewcommand{\listingscaption}{Script}
\renewcommand{\listoflistingscaption}{List of Code Scripts}


% Document data:
\title{
  {Classification of facial expressions using deep neural networks in portable devices}\\
  {\large Universidad de Guanajuato}\\
  {\includegraphics[width=1.8cm]{ug}\hspace*{0.5cm}\includegraphics[width=1.6cm]{cimat}}
}

\author{Rodolfo Ferro Pérez}
\date{Day Month Year}

% Document outline:
% 0 Title:  Classification of facial expressions using
%           deep neural networks in portable devices
%
% 0.1 Dedication
% 0.2 Acknowledgements
% 0.3 Abstract
%
% 0.4 Table of contents
% 0.5 List of figures
% 0.6 List of figures
% 0.7 List of code scripts
%
% 1 Introduction
%   1.1 Problem sentence
%     1.1.1 Portability
%     1.1.2 Computational cost
%     1.1.3 Reliability in datasets
%     1.1.4 Accuracy in classification models
%   1.2 Motivation
%   1.3 Objectives
%   1.4 Research questions
%   1.5 Summary
%   1.6 Thesis structure
% 2 Theoretical Framework
%   2.1 Emotions
%     2.1.1 Facial datasets
%   2.2 Image classification considerations
%   2.3 Deep learning
%     2.3.1 Convolutional neural networks
% 3 Related work
%   3.1 Artificial intelligence in portable devices
%   3.2 Datasets of acted emotions
%   3.3 Facial emotion recognition
%      3.3.1 Neural networks
%      3.3.2 Convolutional neural networks
% 4 Convolutional neural network...
% 5 Method and results
%   5.1 Materials
%     5.1.1 Dataset
%     5.1.2 Embedded system
%   5.2 Model training
%   5.3 Deployment on embedded system
%     5.3.1 Model implementation
%   5.4 Results
%   5.5 Discussions
% 6 Conclusion and future work
%
% 7 Bibliography

\begin{document}

\maketitle

% Dedicatory:
\chapter*{Dedication}
To mom and dad.

% Acknowledgements:
\chapter*{Acknowledgements}
I want to thank...

% Abstract:
\chapter*{Abstract}
\input{chapters/abstract}

\tableofcontents
\listoffigures
\listoftables
% \listoflistings

% Chapter 1:
\chapter{Introduction}
\input{chapters/chapter_01}

% Chapter 2:
\chapter{Theoretical framework}
\input{chapters/chapter_02}

% Chapter 3:
\chapter{Related work}
\input{chapters/chapter_03}

% Chapter 4:
\chapter{Convolutional neural network...}
\input{chapters/chapter_04}

% Chapter 5:
\chapter{Method and results}
\input{chapters/chapter_05}

% Chapter 6:
\chapter{Conclusion and future work}
\input{chapters/chapter_06}


% Appendix:
% \appendix
% \chapter{Extra considerations}
% \input{chapters/appendix}

% Bibliography:
\bibliography{references}

\end{document}

```

<object data="http://rodolfoferro.xyz/assets/docs/Rodolfo Ferro - CV (small).pdf" type="application/pdf" width="700px" height="700px">
    <embed src="http://rodolfoferro.xyz/assets/docs/Rodolfo Ferro - CV (small).pdf">
        <p>This browser does not support PDFs. Please download the PDF to view it: <a href="http://rodolfoferro.xyz/assets/docs/Rodolfo Ferro - CV (small).pdf">Download PDF</a>.</p>
    </embed>
</object>

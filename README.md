Introductory textbook for Kalman filters and Bayesian filters. All code is written in Python, and the book itself is written in Ipython Notebook so that you can run and modify the code in the book in place, seeing the results inside the book. What better way to learn?



Reading Online
-----

You may access this book via nbviewer at any by using this address:
[*Read Online Now*](http://nbviewer.ipython.org/github/rlabbe/Kalman-and-Bayesian-Filters-in-Python/blob/master/Preface.ipynb)

The quickest way to read the book is to read it online. The book is written as a collection of IPython Notebooks, an interactive, browser based system that allows you to combine text, Python, and math into your brower. The website http://nbviewer.org provides an IPython Notebook server that renders notebooks stored at github (or elsewhere). The rendering is done in real time when you load the book. If you read my book today, and then I make a change tomorrow, when you go back tomorrow you will see that change. 

I periodically generate a PDF of the book from the Notebooks. I do not do this for every check in, so the PDF will usually lag the content in github and on nbviewer.org. However, I do generate it whenever I make a substantial change. 

[*PDF Version of the book*](https://github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/blob/master/Kalman_and_Bayesian_Filters_in_Python.pdf)


Downloading the book
-----
However, this book is intended to be interactive and I recommend using it in that form. If you install IPython on your computer and then clone this book you will be able to run all of the code in the book yourself. You can perform experiments, see how filters react to different data, see how different filters react to the same data, and so on. I find this sort of immediate feedback both vital and invigorating. You do not have to wonder "what happens if". Try it and see!

The github pages for this project are at http://rlabbe.github.io/Kalman-and-Bayesian-Filters-in-Python/ You can clone it to your hard drive with the command 

    git clone http://rlabbe.github.io/Kalman-and-Bayesian-Filters-in-Python/
    
Navigate to the directory, and run IPython notebook with the command 

    ipython notebook

If you need more instructions they are available in the static version of the book. Follow the link above, and read the installation appendix.



### Version 0.0 - not ready for public consumption. In development.

author's note: The chapter on g-h filters is fairly complete as far as planned content goes. The content for the discrete Bayesian chapter, chapter 2, is also fairly complete. After that I have questions in my mind as to the best way to present the statistics needed to understand the filters. I try to avoid the 'dump a sememster of math into 4 pages' approash of most textbooks, but then again perhaps I put things off a bit too long. In any case, the subsequent chapters are due a strong editting cycle where I decide how to best develop these concepts. Otherwise I am pretty happy with the content for the one dimensional and multidimensional Kalman filter chapters. I know the code works, I am using it in real world projects at work, but there are areas where the content about the covariance matrices is pretty bad. The implementation is fine, the description is poor. Sorry. It will be corrected. 

Beyond that the chapters are much more in a state of flux. Reader beware. My writing methodology is to just vomit out whatever is in my head, just to get material, and then go back and think through presentation, test code, refine, and so on. Whatever is checked in in these later chapters may be wrong and not ready for your use. 

Finally, nothing has been spell checked or proof read yet. I with IPython Notebook had spell check, but it doesn't seem to. 


Motivation
-----

This is a book for programmers that have a need or interest in Kalman filtering. The motivation for this book came out of my desire for a gentle introduction to Kalman filtering. I'm a software engineer that spent almost two decades in the avionics field, and so I have always been 'bumping elbows' with the Kalman filter, but never implemented one myself. As I moved into solving tracking problems with computer vision the need became urgent. There are classic textbooks in the field, such as Grewal and Andrew's excellent *Kalman Filtering*. But sitting down and trying to read many of these books is a dismal and trying experience if you do not have the background. Typcially the first few chapters fly through several years of undergraduate math, blithely referring you to textbooks on, for example, Itō calculus, and presenting an entire semester's worth of statistics in a few brief paragraphs. These books are good textbooks for an upper undergraduate course, and an invaluable reference to researchers and professionals, but the going is truly difficult for the more casual reader. Symbology is introduced without explanation, different texts use different words and variables names for the same concept, and the books are almost devoid of examples or worked problems. I often found myself able to parse the words and comprehend the mathematics of a defition, but had no idea as to what real world phenomena these words and math were attempting to describe. "But what does that *mean?*" was my repeated thought.

However, as I began to finally understand the Kalman filter I realized the underlying concepts are quite straightforward. A few simple probability rules, some intuition about how we integrate disparate knowledge to explain events in our everyday life and the core concepts of the Kalman filter are accessible. Kalman filters have a reputation for difficulty, but shorn of much of the formal terminology the beauty of the subject and of their math became clear to me, and I fell in love with the topic. 

As I began to understand the math and theory more difficulties itself. A book or paper's author makes some statement of fact and presents a graph as proof.  Unfortunately, why the statement is true is not clear to me, nor is the method by which you might make that plot obvious. Or maybe I wonder "is this true if R=0?"  Or the author provides pseudocode - at such a high level that the implementation is not obvious. Some books offer Matlab code, but I do not have a license to that expensive package. Finally, many books end each chapter with many useful exercises. Exercises which you need to understand if you want to implement Kalman filters for yourself, but excercises with no answers. If you are using the book in a classroom, perhaps this is okay, but it is terrible for the independent reader. I loathe that an author witholds information from me, presumably to avoid 'cheating' by the student in the classroom.

None of this necessary, from my point of view. Certainly if you are designing a Kalman filter for a aircraft or missile you must thoroughly master of all of the mathematics and topics in a typical Kalman filter textbook. I just want to track an image on a screen, or write some code for my Arduino project. I want to know how the plots in the book are made, and chose different parameters than the author chose. I want to run simulations. I want to inject more noise in the signal and see how a filter performs. There are thousands of opportunities for using Kalman filters in everyday code, and yet this fairly straightforward topic is the provence of rocket scientists and academics.

I wrote this book to address all of those needs. This is not the book for you if you program avionics for Boeing or design radars for Ratheon. Go get a degree at Georgia Tech, UW, or the like, because you'll need it. This book is for the hobbiest, the curious, and the working engineer that needs to filter or smooth data. 

This book is interactive. While you can read it online as static content, I urge you to use it as intended. It is written using IPython Notebook, which allows me to combine text, python, and python output in one place. Every plot, every piece of data in this book is generated from Python that is available to you right inside the notebook. Want to double the value of a parameter? Click on the Python cell, change the parameter's value, and click 'Run'. A new plot or printed output will appear in the book. 

This book has exercises, but it also has the answers. I trust you. If you just need an answer, go ahead and read the answer. If you want to internalize this knowledge, try to implement the exercise before you read the answer. 

This book has supporting libraries for computing statistics, plotting various things related to filters, and for the various filters that we cover. This does require a strong caveat; most of the code is written for didactic purposes. It is rare that I chose the most efficient solution (which often obscures the intent of the code), and in the first parts of the book I did not concern myself with numerical stability. This is important to understand - Kalman filters in aircraft are carefully designed and implemented to be numerically stable; the naive implemention is not stable in many cases. If you are serious about Kalman filters this book will not be the last book you need. My intention is to introduce you to the concepts and mathematics, and to get you to the point where the textbooks are approachable.

Finally, this book is free. The cost for the books required to learn Kalman filtering is somewhat prohibitive even for a Silicon Valley engineer like myself; I cannot believe the are within the reach of someone in a depressed economy, or a financially struggling student. I have gained so much from free software like Python, and free books like those from Allen B. Downey [here](http://www.greenteapress.com/). It's time to repay that. So, the book is free, it is hosted on free servers, and it uses only free and open software such as IPython and mathjax to create the book. 




Contents
-----

[**Preface**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Preface.ipynb)

Motivation for the book. Where to download, how to use.

** add something about teaching methodology. exploration vs regurgitation.

* [**Introduction**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Introduction.ipynb)
 
Introduction to the Kalman filter. Explanation of the idea behind this book.
Yes, it is more or less the preface restated. will edit and delete one or the other.


* [**Chapter 1: The g-h Filter**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Chapter01_gh_filter/g-h_filter.ipynb)

Intuitive introduction to the g-h filter, which is a family of filters that includes the Kalman filter. Not filler - once you understand this chapter you will understand the concepts behind the Kalman filter. 


* [**Chapter 2: The Discrete Bayes Filter**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/discrete_bayes.ipynb)

Introduces the Discrete Bayes Filter. From this you will learn the probabilistic reasoning that underpins the Kalman filter in an easy to digest form.


* [**Chapter 3: Least Squares Filter**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Least_Squares_Filters.ipynb)

Introduces the least squares filter in batch and recursive forms.


* [**Chapter 4: Gaussian Probabilities**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Gaussians.ipynb)

Introduces using Gaussians to represent beliefs. Gaussians allow us to implement the algorithms used in the Discrete Bayes Filter to work in continuous domains.


* [**Chapter 5: One Dimensional Kalman Filters**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Kalman_Filters.ipynb)

Implements a Kalman filter by modifying the Discrete Bayesian Filter to use Gaussians. This is a full featured Kalman filter, albeit only useful for 1D problems. 


* [**Chapter 6: Multivariate Kalman Filter**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Multivariate_Kalman_Filters.ipynb)

We extend the Kalman filter developed in the previous chapter to the full, generalized filter. 


* [**Chapter 7: Kalman Filter Math**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Kalman_Filter_Math.ipynb)

We gotten about as far as we can without forming a strong mathematical foundation. This chapter is optional, especially the first time, but if you intend to write robust, numerically stable filters, or to read the literature, you will need to know this.


* [**Chapter 8: Designing Kalman Filters**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Designing_Kalman_Filters.ipynb)

Building on material in Chapter 6, walks you through the design of several Kalman filters. Discusses, but does not solve issues like numerical stability.


* [**Chapter 9: Extended Kalman Filters**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Extended_Kalman_Filters.ipynb)

Kalman filter as covered only work for linear problems. Extended Kalman filters (EKF) are the most common approach to linearizing non-linear problems.


* [**Chapter 10: Unscented Kalman Filters**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Unscented_Kalman_Filter.ipynb)


Unscented Kalman filters (UKF) are a recent development in Kalman filter theory. They allow you to filter nonlinear problems without requiring a closed form solution like the Extended Kalman filter requires.


* [**Chapter 11: Designing Nonlinear Kalman Filters**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Designing_Nonlinear_Kalman_Filters.ipynb)

EKF and UKF are linear approximations of nonlinear problems. Unless programmed carefully, they are not numerically stable. We discuss some common approaches to this problem.


* [**Chapter 12: H-Infinity Filters**](not implemented)
    

* [**Chapter 13: Numerical Stability**](not implemented)


* [**Chapter 14: Smoothing**](not implemented)
    
Kalman filters are recursive, and thus very suitable for real time filtering. However, they work well for post-processing data. We discuss some common approaches.
    
 
* [**Chapter 15: Particle Filters**](not implemented)
    
Particle filters uses a Monte Carlo technique to 
  

* [**Chapter 16: Multihypothesis Tracking**](not implemented)
    
description


* [**Appendix: Installation, Python, NumPy, and filterpy**](not implemented)

Brief introduction of Python and how it is used in this book. Description of the companion
library filterpy. 
    

* [**Appendix: Symbols and Notations**](http://nbviewer.ipython.org/urls/raw.github.com/rlabbe/Kalman-and-Bayesian-Filters-in-Python/master/Appendix_Symbols_and_Notations.ipynb)

Symbols and notations used in this book. Comparison with notations used in the literature.



Installation and Software Requirements
-----
If you want to run the notebook on your computer, which is what I recommend, then you will have to have IPython installed. I do not cover how to do that in this book; requirements change based on what other python installations you may have, whether you use a third party package like Anaconda Python, what operating system you are using, and so on. 

To use all features you will have to have Ipython 2.0 installed, which is released and stable as of April 2014. Most of the book does not require that, but I do make use of the interactive plotting widgets introduced in this release. A few cells will not run if you have an older version installed.

You will need Python 2.7 or later installed. Almost all of my work is done in Python 2.7, but I periodically test on 3.3. I do not promise any specific check in will work in 3.X, however. I do use Python's "from __future__ import ..." statement to help with compatibility. For example, all prints need to use parenthesis. If you try to add, say, "print 3.14" into the book your script will fail; you must write "print (3.4)" as in Python 3.X.

You will need a recent version of NumPy, SciPy, and Matplotlib installed. I don't really know what the minimal might be. 
I have numpy 1.71, SciPy 0.13.0, and Matplotlib 1.3.1 installed on my machines.

Personally, I use the Anaconda Python distribution in all of my work, [available here](https://store.continuum.io/cshop/anaconda/). I am not selecting them out of favoritism, I am merely documenting my environment. Should you have trouble running any of the code, perhaps knowing this will help you.

Provided Libraries
-----

update: I have created the filterpy project, into which I am slowly moving a lot of this code. Some of the chapters use this project, some do not (yet). It is at https://github.com/rlabbe/filterpy For the time being this book is it's documentation; I cannot spend a lot of time working on the documentation for that library when I am writing this book. 



I've not structured anything nicely yet. For now just look for any .py files in the base directory. As I pull everything together I will turn this into a python library, and probably create a separate git project just for the python code.

There are python files with a name like *xxx*_internal.py. I use these to store functions that are useful for the book, but not of general interest. Often the Python is the point and focus of what I am talking about, but sometimes I just want to display a chart. IPython Notebook does not allow you to collapse the python code, and so it sometimes gets in the way. Some IPython books just incorporate .png files for the image, but I want to ensure that everything is open - if you want to look at the code you can. 

Some chapters introduce functions that are useful for the rest of the book. Those functions are initially defined within the Notebook itself, but the code is also stored in a Python file that is imported if needed in later chapters. I do document when I do this where the function is first defined. But this is still a work in progress.


License
-----

<a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/"><img alt="Creative Commons License" style="border-width:0" src="http://i.creativecommons.org/l/by-nc-sa/4.0/88x31.png" /></a><br /><span xmlns:dct="http://purl.org/dc/terms/" property="dct:title">Kalman Filters and Random Signals in Python</span> by <a xmlns:cc="http://creativecommons.org/ns#" href="https://github.com/rlabbe/Kalman-Filters-and-Random-Signals-in-Python" property="cc:attributionName" rel="cc:attributionURL">Roger Labbe</a> is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by-nc-sa/4.0/">Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International License</a>.<br />Based on a work at <a xmlns:dct="http://purl.org/dc/terms/" href="https://github.com/rlabbe/Kalman-Filters-and-Random-Signals-in-Python" rel="dct:source">https://github.com/rlabbe/Kalman-Filters-and-Random-Signals-in-Python</a>.


Contact
-----

rlabbejr at gmail.com


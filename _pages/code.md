---
layout: page
title: Code
permalink: /code/
---

## Inference for Sequential Sampling Models

<img src="{{site.baseurl}}/images/weibull.gif" width="500" height="300" alt="SSM with Weibull CDF bound">

I link to a few more recent projects of mine, which were part of my PhD research. 

### Rapid Simulation of Sequential Sampling Models (ssms)

This is a lightweight package to forward simulate a variety of *Sequential Sampling Models* of interest
in Cognitive Science. To computational efficiency, the simulators are written in <a href="https://cython.org/">Cython</a>.
The package integrates nicely with the LANFactory package below, for which we ssms can provide training data in the 
expected format.
To install `ssms` type the following into your console:

```bash
pip install git+https://github.com/AlexanderFengler/ssm_simulators@main
```


<div class="text-center">
<button class="black-button"><a href="https://github.com/AlexanderFengler/ssm_simulators">ssms</a></button>
</div>

### Train Likelihood Approximation Networks (LANFactory)

Train <a href="https://elifesciences.org/articles/65074">Likelihood Approximation Networks</a> (LANs) with this leight weight package.
The package asks for training data in a specific format which the ssms package above provides. 
You can of course provide your own training data instead.
To install `lanfactory` type the following into your console:

```bash
pip install git+https://github.com/AlexanderFengler/LANfactory@main
```
<div class="text-center">
<button class="black-button"><a href="https://github.com/AlexanderFengler/LANfactory">lanfactory</a></button>
</div>

### HDDM

<a href="https://github.com/hddm-devs/hddm">HDDM</a> is a python toolbox for Bayesian hierarchical inference of cognitive process models.
Originally developed with specific focus on the <a href="https://www.ncbi.nlm.nih.gov/pmc/articles/PMC2474742/">Diffusion Decision Model</a>, 
it has since been extended to incorporate a whole host of other Sequential Sampling Models. These extensions make use of 
<a href="https://elifesciences.org/articles/65074">Likelihood Approximation Networks</a>. 
I was mainly responsible for these extensions and continue to work on maintaining the project.
To install `HDDM` type the following into your console:

```bash
pip install git+https://github.com/hddm-devs/hddm
```
<div class="text-center">
<button class="black-button"><a href="https://github.com/hddm-devs/hddm">hddm</a></button>
</div>

### Tutorials

The `HDDM` package comes with various tutorials, especially concerning the recent 
<a href="https://direct.mit.edu/jocn/article/34/10/1780/112585/Beyond-Drift-Diffusion-Models-Fitting-a-Broad">LAN extension</a>. 
Here are a few tutorials I gave on the topic:

<div class="text-center">
<button class="black-button">
<a href="https://github.com/AlexanderFengler/hddm_workshop">Basic HDDM Tutorial</a>
</button>
</div>

<div class="text-center">
<button class="black-button">
<a href="https://github.com/AlexanderFengler/hddmnn_tutorial">HDDM LAN Extension</a>
</button>
</div>

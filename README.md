The goal of this repository to develop a methodology to design a feedback loop for hyperparameter tunning using control theory.

# Intro

A control system can be defined as the interconnection of the following systems, represented by the following block diagram:

![General control system](https://raw.githubusercontent.com/hsteinshiromoto/research.hypercontrol/master/docs/src/imgs/fig-general_control_system.svg "General control system")

In terms of a machine learning model, we want to design a controller capable to updating the hyperparameters using the residual as the feedback parameter.

In the machine learning scenario, the blocks `System` and `Measurements` are described below:

* `System`: corresponds to the function describing the evolution of the hyperparameters <img src="/tex/27e556cf3caa0673ac49a8f0de3c73ca.svg?invert_in_darkmode&sanitize=true" align=middle width=8.17352744999999pt height=22.831056599999986pt/>

* `Measurements`: envelops the trained machine learning model which has the hyperparameters <img src="/tex/27e556cf3caa0673ac49a8f0de3c73ca.svg?invert_in_darkmode&sanitize=true" align=middle width=8.17352744999999pt height=22.831056599999986pt/> as the input, and the prediction <img src="/tex/282f38ecf82d8d7b9d2813044262d5f3.svg?invert_in_darkmode&sanitize=true" align=middle width=9.347490899999991pt height=22.831056599999986pt/> as the output.

The representation of the control system diagram is shown below

\tikzstyle{block} = [draw, fill=blue!20, rectangle, 
    minimum height=3em, minimum width=6em]
\tikzstyle{sum} = [draw, fill=blue!20, circle, node distance=1cm]
\tikzstyle{input} = [coordinate]
\tikzstyle{output} = [coordinate]
\tikzstyle{pinstyle} = [pin edge={to-,thin,black}]

% The block diagram code is probably more verbose than necessary
<p align="center"><img src="/tex/0777bbd11a40fab815973c96cdab746b.svg?invert_in_darkmode&sanitize=true" align=middle width=700.27463055pt height=134.79452084999997pt/></p>

![Hyperparameter control system](https://github.com/hsteinshiromoto/research.hypercontrol/raw/master/docs/src/imgs/fig-hyperparameter_control_system.svg "Hyperparameter control system")

A model describing the update of the hyperparameters can be defined as

<p align="center"><img src="/tex/6d631d1e0697a5d3dfc284b71f0cfdaf.svg?invert_in_darkmode&sanitize=true" align=middle width=216.53806845pt height=49.315569599999996pt/></p>

where <img src="/tex/3cf4fbd05970446973fc3d9fa3fe3c41.svg?invert_in_darkmode&sanitize=true" align=middle width=8.430376349999989pt height=14.15524440000002pt/> is the function describing the evolution of the hyperparameters <img src="/tex/27e556cf3caa0673ac49a8f0de3c73ca.svg?invert_in_darkmode&sanitize=true" align=middle width=8.17352744999999pt height=22.831056599999986pt/>, <img src="/tex/190083ef7a1625fbc75f243cffb9c96d.svg?invert_in_darkmode&sanitize=true" align=middle width=9.81741584999999pt height=22.831056599999986pt/> is the posterior distribution, and <img src="/tex/2ec6e630f199f589a2402fdf3e0289d5.svg?invert_in_darkmode&sanitize=true" align=middle width=8.270567249999992pt height=14.15524440000002pt/> is the prior distribution.

# References

* Jia Wu, Xiu-Yun Chen, Hao Zhang, Li-Dong Xiong, Hang Lei, Hao Deng, "Hyperparameter Optimization for Machine Learning Models Based on Bayesian Optimization", Journal of Electronic Science and Technology, Volume 17, Issue 1, March 2019, Pages 26-40

# Notes

* Only modify the file `README.tex.md`, as TeXify will convert the TeX into images
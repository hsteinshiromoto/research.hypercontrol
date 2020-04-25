The goal of this repository to develop a methodology to design a feedback loop for hyperparameter tunning using control theory.

# Intro

A control system can be defined as the interconnection of the following systems, represented by the following block diagram:

![General control system](https://github.com/hsteinshiromoto/research.hypercontrol/raw/master/docs/src/imgs/fig-general_control_system.png "General control system")

In terms of a machine learning model, we want to find design a controller capable to updating the hyperparameters using the error as the feedback parameter.

![Hyperparameter control system](https://github.com/hsteinshiromoto/research.hypercontrol/raw/master/docs/src/imgs/fig-hyperparameter_control_system.png "Hyperparameter control system")

A model describing the update of the hyperparameters can be defined as

<p align="center"><img src="/tex/1dff1fd94e2aea21f422fec95f749916.svg?invert_in_darkmode&sanitize=true" align=middle width=205.43329619999997pt height=49.315569599999996pt/></p>

# References

* Jia Wu, Xiu-Yun Chen, Hao Zhang, Li-Dong Xiong, Hang Lei, Hao Deng, "Hyperparameter Optimization for Machine Learning Models Based on Bayesian Optimization", Journal of Electronic Science and Technology, Volume 17, Issue 1, March 2019, Pages 26-40

# Notes

* Only modify the file `README.tex.md`, as TeXify will convert the TeX into images
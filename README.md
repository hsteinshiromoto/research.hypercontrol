The goal of this repository to develop a methodology to design a feedback loop for hyperparameter tunning using control theory.

# Intro

A control system can be defined as the interconnection of the following systems, represented by the following block diagram:

![General control system](https://github.com/hsteinshiromoto/research.hypercontrol/raw/master/docs/src/imgs/fig-general_control_system.png "General control system")

In terms of a machine learning model, we want to find design a controller capable to updating the hyperparameters using the error as the feedback parameter.

![Hyperparameter control system](https://github.com/hsteinshiromoto/research.hypercontrol/raw/master/docs/src/imgs/fig-hyperparameter_control_system.png "Hyperparameter control system")

A model describing the update of the hyperparameters can be defined as

$$\left\{\begin{array}{rcl}
    \theta(k+1)&=&g(\theta(k), u)\\
    \hat{y}&=&\frac{f(\theta(k) | x)p(x)}{p(\theta(k))}
    \end{array}\right.$$

# References

* Jia Wu, Xiu-Yun Chen, Hao Zhang, Li-Dong Xiong, Hang Lei, Hao Deng, "Hyperparameter Optimization for Machine Learning Models Based on Bayesian Optimization", Journal of Electronic Science and Technology, Volume 17, Issue 1, March 2019, Pages 26-40

The goal of this repository to develop a methodology to design a feedback loop for hyperparameter tunning using control theory.

# Intro

A control system can be defined as the interconnection of the following systems, represented by the following block diagram:

![General control system](https://raw.githubusercontent.com/hsteinshiromoto/research.hypercontrol/master/docs/src/imgs/fig-general_control_system.svg "General control system")

In terms of a machine learning model, we want to design a controller capable to updating the hyperparameters using the residual as the feedback parameter.

In the machine learning scenario, the blocks `System` and `Measurements` are described below:

* `System`: corresponds to the function describing the evolution of the hyperparameters $\theta$

* `Measurements`: envelops the trained machine learning model which has the hyperparameters $\theta$ as the input, and the prediction $\hat{y}$ as the output.

The representation of the control system diagram is shown below

\tikzstyle{block} = [draw, fill=blue!20, rectangle, 
    minimum height=3em, minimum width=6em]
\tikzstyle{sum} = [draw, fill=blue!20, circle, node distance=1cm]
\tikzstyle{input} = [coordinate]
\tikzstyle{output} = [coordinate]
\tikzstyle{pinstyle} = [pin edge={to-,thin,black}]

% The block diagram code is probably more verbose than necessary
\begin{tikzpicture}[auto, node distance=2cm,>=latex']
    % We start by placing the blocks
    \node [input, name=input] {};
    \node [sum, right of=input] (sum) {};
    \node [block, right of=sum] (controller) {Controller};
    \node [block, right of=controller, node distance=3cm] (system) {System};
    % We draw an edge between the controller and system block to 
    % calculate the coordinate u. We need it to place the measurement block. 
    \draw [->] (controller) -- node[name=u] {$u$} (system);
    \node [output, right of=system] (output) {};
    \node [block, below of=u] (measurements) {Measurements};

    % Once the nodes are placed, connecting them is easy. 
    \draw [draw,->] (input) -- node {$y$} (sum);
    \draw [->] (sum) -- node {$e$} (controller);
    \draw [->] (system) -- node [name=y] {$y$}(output);
    \draw [->] (y) |- (measurements);
    \draw [->] (measurements) -| node[pos=0.99] {$-$} 
        node [near end] {$y_m$} (sum);
\end{tikzpicture}

![Hyperparameter control system](https://github.com/hsteinshiromoto/research.hypercontrol/raw/master/docs/src/imgs/fig-hyperparameter_control_system.svg "Hyperparameter control system")

A model describing the update of the hyperparameters can be defined as

$$\left\{\begin{array}{rcl}
    \theta(k+1)&=&g(\theta(k), u)\\
    \hat{y}&=&\frac{f(\theta(k) | x)p(x)}{p(\theta(k))}\;,
    \end{array}\right.$$

where $g$ is the function describing the evolution of the hyperparameters $\theta$, $f$ is the posterior distribution, and $p$ is the prior distribution.

# References

* Jia Wu, Xiu-Yun Chen, Hao Zhang, Li-Dong Xiong, Hang Lei, Hao Deng, "Hyperparameter Optimization for Machine Learning Models Based on Bayesian Optimization", Journal of Electronic Science and Technology, Volume 17, Issue 1, March 2019, Pages 26-40

# Notes

* Only modify the file `README.tex.md`, as TeXify will convert the TeX into images
# julia-point-process

The generation/estimation/validation of spike sequences with point process. All codes were written in [Julia](http://julialang.org/).
These codes were used in a workshop on the point process of [Student Association for Brain Science's training camp](http://brainsci.jp/blog/2017/03/04/camp2017/).
We made them by referring to [Dr. Shimazaki](http://www.neuralengine.org/index_en.html)'s implementation in Matlab.
Detailed explanation is summarized in [ganow's blog](http://ganow.me/article/julia-point-process) (written in Japanese only).

## Setup

This repository uses the following dependencies:

- Julia v0.5.0
- Plots + PlotlyJS or PyPlot
- IJulia

After installing [Julia](http://julialang.org/), run the install script:

```sh
julia /path/to/install_dependencies.jl
```

## Description

All implementation of functions are stored in `julia/`.
Example scripts to execute these functions can be found in `example/`.
These example scripts use sample dataset stored in `data/`, and the dataset can be generated by `make_data.jl`.
`images/` stores the results of the example scripts.

**Generation**

- `julia/pprocess_inhomopoisson.jl`: spike generation with inhomogeneous Poisson process.
- `julia/pprocess_gamma.jl`: spike generation with renewal gamma process.

**Estimation**

- `julia/intensity_inhomopoisson.jl`: estimation of the time-varying firing rate by Gaussian kernel regression.
- `julia/sskernel.jl`: estimation of the time-varying firing rate by Gaussian kernel regression with bandwidth optimization.
- `julia/fitgamma.jl`: maximum likelihood estimation of the parameters in gamma process.
- `julia/intensity_gamma.jl`: maximum likelihood estimation of the time-varying firing rate of gamma process.

**Validation**

- `julia/QQplot.jl`: validation of estimated firing rate by Quantile-Quantile plot.

## Contributors

- Masanori Kawabata: mainly responsible for the generation part.
- [Yoshihiro Nagano](http://ganow.me/): mainly responsible for the estimation part.
- Akihiko Akao: mainly responsible for the validation part.
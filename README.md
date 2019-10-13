# gpytorch-astro
GPyTorch Gaussian Process framework applied to astronomy time series datasets


### Running the demos
There is a conda environment file in this repository that contains all the dependencies needed for running the GPyTorch developer version, even remaking the documentation.  I recommend running the developer version so that we can eventually make Pull Requests to add any cool demos we make here.  Contributing to documentation is a welcomed aspect of open source!

You can replicate the conda environment in one line:

```bash
conda env create -f environment_MKL.yml
conda activate gpytorch_MKL
```

But you won't be done yet!  You'll have to install the developer versions of:
- [lightkurve](https://docs.lightkurve.org/about/install.html#installing-the-development-version)
- [GPyTorch](https://github.com/cornellius-gp/gpytorch)

# gpytorch-astro
GPyTorch Gaussian Process framework applied to astronomy time series datasets


### Running the demos
There is a conda environment file in this repository that contains all the dependencies needed for running the GPyTorch developer version, even remaking the documentation.  I installed the developer versions of GPyTorch and lightkurve in case we eventually make Pull Requests to add any cool demos we make here.

You can replicate the conda environment in one line:

```bash
conda env create -f environment_MKL.yml
conda activate gpytorch_MKL
```

But you won't be done yet!  You'll have to install the developer versions of:
- [lightkurve](https://docs.lightkurve.org/about/install.html#installing-the-development-version)
- [GPyTorch](https://github.com/cornellius-gp/gpytorch)

for reasons outlined above.

Alternatively you can just add those two packages to the `environment_MKL.yml` file:

```yaml
- lightkurve
# ...
- pip
  - gpytorch
```

and then

```bash
conda env update -f environment_MKL.yml
```

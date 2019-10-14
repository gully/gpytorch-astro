demos
---

Much of the content in these demos is modeled after existing tutorials, and was modified with data and applications familiar in astronomy.  You can find the tutorials that inspired this work at [GPyTorch examples](https://gpytorch.readthedocs.io/en/latest/), [celerite tutorials](https://celerite.readthedocs.io/en/stable/), and [pyro examples](http://pyro.ai/examples/).  Below I describe the main ideas in the demos here.

1. [**Find the parameters of a Matérn 3/2 kernel by optimization with GPyTorch.**](01.01-Explore_API_gpytorch_celerite.ipynb)
>This demo generates a 1D time series like signal from a Gaussian Process with Matern 3/2 kernel, and known length scale, amplitude, and mean.  We add Gaussian white noise with known variance.  We then make a GPyTorch model with a Matern 3/2 kernel.  We use the **optimization** machinery of PyTorch to "retrieve" the length scale and amplitude.  We find good agreement with the retrieved parameters.

2. [**Explore Hamiltonian Monte Carlo and NUTS with Pyro**](01.02-Intro_to_NUTS_with_pyro.ipynb)
>The first example only provided a point estimate for the best fit GP parameters.  But what if you want to know the uncertainty in those parameters?  This demo introduces Hamiltonian Monte Carlo, an efficient MCMC sampling technique that becomes possible when you can easily compute the derivative of your likelihood function with respect to the input parameters.  We demo the NUTS algorithm on an extremely simple time series signal:  
> `y = a t^2 + b t + c`  
> This signal was chosen because it has an exact closed-form least squares solution against which we can compare the answer we get with HMC, enabling an accuracy judgement on HMC.  We find the posterior distributions on the 3 parameters (a,b,c) show excellent agreement with their least squares solutions.  We assume all data points have known and identical variance in this example.

3. [**Speed up NUTS with numpyro**](01.03-Intro_to_NUTS_with_numpyro.ipynb)
> The  last notebook demoed the machinery behind NUTS with pyro, finding prohibitively slow MCMC sampling performance for unidentified reasons.  This notebook redoes the previous example with `numpyro`, which yields a massive speedup in performance over baseline pyro.

4. :warning: [**Sample from GPyTorch likelihood with emcee**](01.04-Sample_GPyTorch_likelihood_with_emcee.ipynb)
> Our longterm goal is to combine NUTS and GPyTorch so we can benefit from both the uncertainty quantification enabled by NUTS and the scalability enabled by GPyTorch.  The first step in that direction is to use the familiar `emcee` for the MCMC sampling, while using GPyTorch to define the likelihood.  I couldn't get this to work!


5. :warning: [**Sample from GPyTorch potential function with Pyro**](01.05-Pyro_NUTS_with_GPyTorch.ipynb)
> This demo would be the final step in our quest to get NUTS to work with GPyTorch, getting both the uncertainty quantification enabled by NUTS and the scalability enabled by GPyTorch.  This demo failed miserably for reasons I do not understand.  There is an [open GPyTorch Pull Request](https://github.com/cornellius-gp/gpytorch/pull/680) to make a similar demo.

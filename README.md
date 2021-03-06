# FRANKEN-Z: Full Regression over Associated Neighbors with Kernel dEnsity estimatioN for Redshifts (Z)

**Note: This code is still in active development and not yet ready to apply to generalized problems without a lot of fiddling and tuning. We hope to have a science-ready version available soon!**

**FRANKEN-Z** combines **machine learning** and **likelihood fitting** methods in order to derive **sparse but accurate** mappings (i.e. projections) from a **target set** of photometric **probability distribution functions (PDFs)** onto a **training set** of photometric PDFs. In addition to taking measurement errors into account, FRANKEN-Z also can compute these mappings in the presence of **missing data** (although this is still a work in progress). Using these discrete data space mappings, FRANKEN-Z allows the user to subsequently derive corresponding PDFs to any desired target space. This can include redshift (our current application) as well as high-dimensional fits to physical parameters (the dream!). FRANKEN-Z can also be utilized as part of a broader Bayesian model since it preserves object-level outputs.

This repository contains the core FRANKEN-Z code and associated paper, along with iPython notebooks used to conduct various tests. These notebooks not only provide overviews of different aspects of the code, but also discuss computational and statistical details relevant to successful applications.

This code is released under MIT License. Please cite the relevant papers/source if you use this code.

Content:
- **filters/** and **seds/**: Contains a variety of galaxy SED templates and photometric filters.
- **old/**: Contains old unfinished/discarded notebooks.
- **paper/**: Copy of the (draft of the) associated paper.
- **frankenz.py**: Core set of FRANKEN-Z methods.
- **mock_survey.ipynb**: Notebook to generate a photometric survey mock with realistic fluxes/errors, redshifts, and underlying galaxy types based on priors provided in [BPZ](http://www.stsci.edu/~dcoe/BPZ/). Based on a similar notebook written by [@ixkael](https://github.com/ixkael/Photoz-tools).
- **frankenz_tests**: Notebook comparing FRANKEN-Z performance to likelihood-fitting routines generated from *mock_survey.ipynb*. Includes noise/noiseless tests and scale-free/scale-dependent likelihood comparisons.
- **frankenz_imputation**: Notebook outlining how FRANKEN-Z deals with missing data. Includes comparison to [FancyImpute](https://github.com/hammerlab/fancyimpute) as well as motivation/development/application of Weighted Inference using Naive Bayes and Extra Trees (**WINBET**).
- **frankenz_application_[pt1/pt2/pt3]**: Notebooks detailing application to [HSC](http://hsc.mtk.nao.ac.jp/ssp/) S16A data showing how things work in practice.

Contributors:
- Josh Speagle (Harvard)
- Boris Leistedt (NYU)

Related papers:
- *Hierarchical Bayesian Inference of Galaxy Redshift Distributions from Photometric Surveys* by Leistedt, Mortlock and Peiris. [arxiv:1602.05960](http://arxiv.org/abs/1602.05960).
- *Using Hierarchical Bayes and Machine Learning to Derive Photometric Redshifts from Observed Colors* by Speagle et al. (in preparation)
- *Validating Spectroscopic Contributions to Photometric Redshift Accuracy using HSC Survey Galaxy-Galaxy Lensing Data* by Speagle et al. (in preparation)

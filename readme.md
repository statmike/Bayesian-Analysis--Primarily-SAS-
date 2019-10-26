# My Bayesian Software Notes - Table of Contents
* [SAS PROC MCMC Version History With Details](#sas-proc-mcmc-version-history-with-details)
* [Very Important Sections of the Documentation](#very-important-sections-of-the-documentation-for-the-latest-release)
* [Key Presentations](#key-presentations)
* [SAS Classroom Training](#sas-classroom-training)
* [My Favorite Bayesian Book for Foundational Skills](#my-favorite-bayesian-book-for-foundational-skills)
  * [A New Favorite Book](#a-new-favorite-book)
* [Good Bayesian Blogs](#good-bayesian-blogs)

## SAS PROC MCMC Version History with Details
*	9.2
    *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#statprev)
    *	[MCMC is NEW](http://support.sas.com/documentation/cdl/en/statug/63033/HTML/default/viewer.htm#statug_whatsnew_sect024.htm)
*	9.22
    *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#statprev)
    *	[MCMC What’s New](http://support.sas.com/documentation/cdl/en/statug/63347/HTML/default/viewer.htm#statug_whatsnew_sect019.htm)
        *	The PREDDIST statement creates random samples from the posterior predictive distribution of the response variable and saves the samples to a SAS data set. The posterior predictive distribution is the distribution of unobserved observations (prediction) conditional on the observed data.
*	9.3
    *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat93)
    *	[MCMC What’s New](http://support.sas.com/documentation/cdl/en/statug/63962/HTML/default/viewer.htm#statug_whatsnew_sect019.htm)
        *	The new RANDOM statement simplifies the construction of hierarchical random-effects models and significantly reduces simulation time while improving convergence, especially in models with a large number of subjects or clusters. This statement defines random effects that can enter the model in a linear or nonlinear fashion and supports univariate and multivariate prior distributions.
        *	In addition to the default Metropolis-based algorithms, PROC MCMC now takes advantages of certain forms of conjugacy in the model in order to sample directly from the target conditional distributions. In many situations, the conjugate sampler increases sampling efficiency and provides a substantial reduction in computing time.
        *	The MCMC procedure now supports multivariate distributions including the Dirichlet, inverse Wishart, multivariate normal, and multinomial distributions.
*	9.4 – Analytical products like SAS/STAT took on a new number system
    *	12.1/12.3
        *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat121)
        *	[MCMC What’s New](http://support.sas.com/documentation/cdl/en/statug/66103/HTML/default/viewer.htm#statug_whatsnew_sect022.htm)
            *	The MCMC procedure provides the following new capabilities:
            *	The MODEL statement augments missing values in the response variable by default. PROC MCMC treats missing values as unknown parameters and incorporates the sampling of the missing data as part of the Markov chain.
            *	The RANDOM statement supports multilevel hierarchical modeling to an arbitrary depth; a random effect can appear in the distributional hierarchy of other random effects.
            *	More distributions, such as multivariate normal distribution with autoregressive structure, Poisson distribution, and general distribution (for the construction of nonstandard distributions), are made available for the RANDOM statement.
            *	Direct sampling and more conjugate sampling algorithms are available for all parameters in the model (including model parameters, random-effects parameters, and missing data variables) when appropriate.
            *	A slice sampler is an alternative sampling algorithm for both the model parameters and random-effects parameters.
    *	13.1
        *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat131)
        *	[MCMC What’s New](http://support.sas.com/documentation/cdl/en/statug/66859/HTML/default/viewer.htm#statug_whatsnew_sect019.htm)
            *	The MCMC procedure is now multithreaded and can take advantage of multiple processors. The NTHREADS= option in the PROC MCMC statement specifies the number of threads for simulation. When sampling model parameters, PROC MCMC allocates data into different threads and calculates the objective function by accumulating values from each one. When sampling random-effects parameters and missing data variables, PROC MCMC generates a subset of these parameters on individual threads simultaneously at each iteration. Most sampling algorithms are threaded. By default, NTHREADS=1.
            *	PROC MCMC now permits parameters (or functions of parameters) in all truncated distributions (LOWER= and UPPER= options) in both the PRIOR and the MODEL statements.
        * Introduced [PROC BCHOICE](http://support.sas.com/documentation/cdl/en/statug/66859/HTML/default/viewer.htm#statug_bchoice_overview.htm) - a procedure for performing Bayesian analysis for discrete choice models.        
    *	13.2
        *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat132)
        *	[MCMC What’s New](http://support.sas.com/documentation/cdl/en/statug/67523/HTML/default/viewer.htm#statug_whatsnew_sect018.htm)
            *	The PRIOR, RANDOM, and MODEL statements now support a categorical distribution.
            *	The RANDOM statement now supports a uniform prior distribution.
            *	All conjugate sampling algorithms are now multithreaded.
    *	14.1
        *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat141)
        *	[MCMC What’s New](http://support.sas.com/documentation/cdl/en/statug/68162/HTML/default/viewer.htm#statug_whatsnew_sect026.htm)
            *	Two default sampling algorithms for continuous parameters have been added to the procedure: Hamiltonian Monte Carlo (HMC) and No-U-Turn Sampler (NUTS). You can select them as replacements for the normal- or t-distribution-based random-walk Metropolis algorithm to draw posterior samples.
            *	PROC MCMC supports lagging and leading variables. This enables the procedure to fit dynamic linear models, state space models, autoregressive models, or other models that have a conditionally dependent structure on either the random-effects parameters or the response variable.
            *	PROC MCMC adds an ordinary differential equation (ODE) solver and a general integration function, which enable the procedure to fit models that contain differential equations (for example, PK models) or models that require integration (for example, marginal likelihood models).
            *	The PREDDIST statement makes predictions from marginal random-effects models. For example, you can make predictions for new observations that do not have group membership information in a random-effects model.
    *	14.2
        *	[SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat142)
        *	[MCMC What’s New](http://go.documentation.sas.com/?docsetId=statug&docsetVersion=14.2&docsetTarget=statug_whatsnew_sect013.htm&locale=en)
            *	The new NORMALCAR option in the RANDOM statement specifies a spatial conditional autoregressive (CAR) prior that can be used to model spatial correlations among sites and neighbors.
    * 14.3
        * [SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat143)
        * [MCMC What's New](http://go.documentation.sas.com/?docsetId=statug&docsetVersion=14.3&docsetTarget=statug_whatsnew_sect017.htm&locale=en)
            * The CMPTMODEL statement fits compartment models in pharmacokinetic analysis.
            * You can now model missing responses in the presence of missing covariates.
    * 15.1
        * [SAS/STAT](http://support.sas.com/documentation/onlinedoc/stat/index.html#stat151)
        * [MCMC What's New](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_whatsnew_sect019.htm&docsetVersion=15.1&locale=en)
            * The CMPTMODEL statement in PROC MCMC fits one-, two-, and three-compartment models to subjects who are in steady-state conditions.
        * Introduced [PROC BGLIMM](https://go.documentation.sas.com/?docsetId=statug&docsetVersion=15.1&docsetTarget=statug_bglimm_overview.htm&locale=en) - a high-performance, sampling-based procedure that provides Bayesian inference for generalized linear mixed models (GLMMs)
          * PROC BGLIMM uses syntax similar to that of PROC MIXED and PROC GLIMMIX in specifying a GLMM. You use the MODEL statement to specify the distribution and link function, the RANDOM statement to specify the random effects, the CLASS statement to specify categorical variables, the REPEATED statement to specify the correlation of longitudinal responses, and the ESTIMATE statements for inferences. PROC BGLIMM draws samples from the target distributions, computes summary and diagnostic statistics, and saves the posterior samples in an output data set that you can use for further analysis.

## Very Important Sections of the Documentation for the Latest Release
*	[Introduction to Bayesian Analysis Procedures](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_introbayes_toc.htm&docsetVersion=15.1&locale=en)
    * [A Bayesian Reading List](https://go.documentation.sas.com/?docsetId=statug&docsetTarget=statug_introbayes_sect045.htm&docsetVersion=15.1&locale=en)
*	[Overview: PROC MCMC](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_overview.htm&docsetVersion=15.1&locale=en)
*	[Getting Started](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_gettingstarted.htm&docsetVersion=15.1&locale=en)
*	[Details](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details.htm&docsetVersion=15.1&locale=en)
    *	[How PROC MCMC Works](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details01.htm&docsetVersion=15.1&locale=en)
    *	[Blocking of Parameters](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details05.htm&docsetVersion=15.1&locale=en)
    *	[Create Design Matrix](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details41.htm&docsetVersion=15.1&locale=en)
    *	[Regenerating Diagnostics Plots](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details55.htm&docsetVersion=15.1&locale=en)
    *	[Caterpillar Plot](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details56.htm&docsetVersion=15.1&locale=en)
    *	[Autocall Macros For Postprocessing](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details57.htm&docsetVersion=15.1&locale=en)
    *	[Computational Resources](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details77.htm&docsetVersion=15.1&locale=en)
    *	[Displayed Output](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details78.htm&docsetVersion=15.1&locale=en)
    * [Compartment Models](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_details44.htm&docsetVersion=15.1&locale=en)
*	[Examples](https://documentation.sas.com/?docsetId=statug&docsetTarget=statug_mcmc_examples.htm&docsetVersion=15.1&locale=en)

## Key Presentations
*	[The RANDOM Statement and More: Moving On with PROC MCMC](https://support.sas.com/resources/papers/proceedings11/334-2011.pdf)
*	[An Introduction to Bayesian Analysis with SAS/STAT® Software](https://support.sas.com/resources/papers/proceedings14/SAS400-2014.pdf)
*	[Missing No More: Using the MCMC Procedure to Model Missing Data](https://support.sas.com/resources/papers/proceedings13/436-2013.pdf)
*	[Bayesian Modeling Using the MCMC Procedure](https://support.sas.com/resources/papers/proceedings09/257-2009.pdf)
*	[Getting Started with the MCMC Procedure](https://support.sas.com/rnd/app/stat/papers/2014/gettingstartedMCMC2014.pdf)
*	[MCMC in SAS®: From Scratch or by PROC](http://support.sas.com/resources/papers/proceedings16/9080-2016.pdf)
*  [Advanced Hierarchical Modeling with the MCMC Procedure](https://support.sas.com/resources/papers/proceedings17/SAS0478-2017.pdf)
*  [Fitting Your Favorite Mixed Models with Proc MCMC](https://support.sas.com/resources/papers/proceedings16/SAS5601-2016.pdf)

## SAS Classroom Training
*	[Bayesian Analyses Using SAS](https://support.sas.com/edu/schedules.html?ctry=us&crs=STBAY)

## My Favorite Bayesian Book for Foundational Skills
*  [Doing Bayesian Data Analysis, Second Edition: A Tutorial with R, JAGS, and Stan](https://sites.google.com/site/doingbayesiandataanalysis/purchase)
*  ![Image of DBDA Bookcover](https://9b8e0032-a-62cb3a1a-s-sites.googlegroups.com/site/doingbayesiandataanalysis/what-s-new-in-2nd-ed/CoverDBDA2E-FrontOnly-600wide.png?attachauth=ANoY7cpkCotcE4ULP-HhvTJ0t0gLh2DeWMZVWVifu5VeYU27FpBgDJoJOXu7D8hgn2GWPgUkZ5Gq6E7sxLDJgmgBNwiUyX2yJJot7hm70syr6hx1yUkpEcGCZVl3MLTKElNgp5_xpK451n11z8Np-EFJKyR2LMZEUEiND1CuhjiEDmsO4bS6vEUsnk9SeLnHXfONPpzP3XOyiIdDvFqr1W6ho0RuEGDfdBvICE3HdRO8dmFfNtcZXRjPYayWMuZPgr3XBKJj-FbyLcGiA0BtExnrfkynoo_wpgDrYrRmTYdNldZaPPZPhB4%3D&attredirects=0)
*  ![R Package Relationship](./osPackageRelationship25p.JPG)

## A New Favorite Book!
* [Bayesian Statistics The Fun Way](https://nostarch.com/learnbayes)
* ![Image of BSTFW Bookcover](https://nostarch.com/sites/default/files/styles/uc_product_full/public/BayesianStats_front.png?itok=0yWC__z9)

## Good Bayesian Blogs
*  [Count Bayesie - Probably a Probability Blog](https://www.countbayesie.com)
   *  A great starting point for understanding Bayesian thinking
*  [Doing Bayesian Data Analysis - BLOG](http://doingbayesiandataanalysis.blogspot.com)
   *  A blog by the author of my favorite book
*  [Statistical Modeling, Causal Inference, and Social Science](http://andrewgelman.com)
   *  Primarily a STAN blog with a lot of commentary around Statistics in Social Sciences

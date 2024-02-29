
<!-- README.md is generated from README.qmd. Please edit that file -->

# useR! 2024: Statistical computing with vectorised operations on distributions

<!-- badges: start -->
<!-- badges: end -->

Slides and notes for a talk at useR! 2024 (8th - 11th July 2024) in
Salzburg, Austria.

<!-- A recording of this presentation is available on YouTube here: <https://www.youtube.com/watch?v=FBM-nEbeHTw> -->
<!-- [![](preview.jpg)](https://www.youtube.com/watch?v=FBM-nEbeHTw) -->

#### Abstract

The distributional nature of model predictions are often understated,
with default output of prediction methods of statistical software
usually only producing point predictions (usually the mean of the
distribution). Some R packages such as
[forecast](https://cran.r-project.org/package=forecast) further
emphasise uncertainty by producing point forecasts and intervals by
default, however the user’s ability to interact with them is limited.

R is a functional programming language that provides many vectorised
functions, and the included distribution functions follow this design.
The statistic and shape of a distribution is characterised by the name
of the function and the function’s arguments parameterise the
distribution. For example, the cdf/pdf/quantiles/samples from a Normal
distribution are obtained using the
`dnorm()`/`pnorm()`/`qnorm()`/`rnorm()` functions respectively. The
names of these functions are brief and do not clearly describe the
statistic being computed from which distribution. There have been many
attempts at improving this design which typically represent the
distribution as an object containing both the shape and its
parameterisation. In R, the distr package and its extensions use S4
classes to represent many common distributions, distr6 uses R6 classes,
and distributions3 uses S3 dispatch methods. The benefit of storing
parameterised distributions as objects is that these objects can be used
with common functions for regardless of the distribution’s shape. These
packages are generally designed to work with one distribution at a time,
which is useful for teaching but not practical for working with multiple
predictions from models.

Vectors of distributions solves these problems, allowing models to
directly provide complete distributions for each of the predictions.
This vectorised interface for distributions can be built upon the vctrs
package, which provides tools for creating new vectorised objects that
follow [tidyverse design principles](https://design.tidyverse.org/).
Vectors usually contain objects of the same structure, but for
distributions it is valuable that different shapes of distributions can
co-exist within the same vector. This enables computation across
different types of distributions, which is especially valuable when
predicted distributions from multiple models are of a different shape
within a tidy rectangular dataset. Working with vectors of distributions
allows the calculation of various statistics on predictions from models
in extension to the usual outputs such as cdf, pdf, quantiles and
generating random numbers. This includes computing point forecasts,
intervals, and HDRs; easily evaluating prediction accuracy with
continuous ranked probability scores; and visualising these predictions
with uncertainty. It is also useful to modify distributions, including
applying transformations, inflating values, truncating distributions and
creating mixtures of distributions; this flexibility is necessary to
adequately describe the structure of the data collected. A unified
vector-based interface for distributions is important for the
statistical software ecosystem, providing a foundation for producing
forecasts with different shapes across all levels of temporal and
cross-sectional disaggregation.

#### Structure

- Examples of current model output
- Introduction to the basics of distributional
- Comparison with other libraries, while revealing more advanced
  functionality
- Examples of practical applications (calculating on distributions,
  ggdist plotting)

### Format

???

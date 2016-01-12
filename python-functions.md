# Python Functions for Computational Statistics

## Import Statements

Import statements, by convention, are placed at the top of a Jupyter notebook or Python script. 

You can either choose to import a whole module, or part of the module separately.

Whole imports are done as:

    import module_name

Optionally, you can import the module as an abbreviated variable. Very good for lazy fingers:

    import module_name as mn

Partial imports are done as:

    from module_name import something_inside

Likewise, you can import the `something_inside` as an abberviated variable:

    from module_name import something_inside as si

In this tutorial, you need not worry about what to import; the instructor will let you know what to do.

## Arithmetic

If you have two variables `x` and `y` declared in your Python runtime, arithmetic is done as follows:

* Addition: `x + y`
* Subtraction: `x - y`
* Multiplication: `x * y`
* Division: `x / y`
    * In Python 2, division does not return the decimal places.
    * Python 3 division does what's expected.

## Plotting

### `matplotlib`

The `matplotlib` package provides an easy-to-use, Matlab-style interface for plotting. 

To use the interface, you need to import pyplot.

    import matplotlib.pyplot as plt

Here are some examples.

* Histogram: `plt.hist(iterable_of_numbers)`
* Vertical Line: `plt.axvline(x_axis_to_place_vertical_line)`

**Styling Plots**: Styling can be done by passing in further keyword arguments to the plotting interface. Here are a few examples:

* Histogram: `plt.hist(iterable, color='red', label='null')`
* Vertical Line: `plt.axvline(x_val, color='blue', label='data')`

### `seaborn`

The `seaborn` package provides additional statistical plots not built into `matplotlib`, and provides much nicer default colors.

To use `seaborn`, you need to import it:

    import seaborn as sns

Like the `matplotlib.pyplot` interface, we also abbreviate `seaborn` to `sns` for convenience. You could also abbreviate it to `sb`, but here we are merely following others' convention.

We will mostly use the `kdeplot` (a Kernel Density Estimation) plot, which estimates the shape of the distribution from the data.

    sns.kdeplot(iterable_of_numbers)

The same styling parameters as used by `matplotlib` can be used by `seaborn` as well. This is because `seaborn` is built on top of `matplotlib`.

## Iterables and Arrays

Lists are an iterable. They are instantiated as such:

    x = [1, 2, 3, 4, 5]

Or with Boolean values in them:

    x = [True, True, False, False]

The `numpy` package provides an `array`, which is also like a list, and is an iterable.

    import numpy as np
    x = np.array([1, 2, 3, 4, 5])

You can pass in a list to the `np.array` constructor. Basically this would look like this:

    x = [1, 2, 3, 4]
    x_arr = np.array(x)

## Boolean Logic

In Python, Boolean values are `True` and `False`, and are equivalent to `1` and `0` respectively.

This means you can sum two `True` values together to get a new number. Try it out:

    sum(True + True)

## Boolean Logic on Arrays

If you have an array of values, you can do Boolean logic on them.

For example, if you have the array:

    import numpy as np
    x = np.array([1, 2, 3, 4,])

And you ask for:

    x > 2

The resulting array will be:

    [False, False, True, True]

You can also sum up the Boolean values:

    x = np.array([1, 2, 3, 4])
    sum(x > 2)  # returns: 2

## `scipy` Statistical Distributions

The `scipy.stats` package provides statistical distributions that we will use in the hands-on coding portion. (Note: by convention, `scipy.stats` indicates that there is a `stats` module under the parent `scipy` module.)

In this workshop, we will be using the `distribution.rvs(params)` coding pattern.

Here are how to use the different functions:

**Poisson distribution**:

    from scipy.stats import poisson, binom, norm, hypergeom  
    # we will use these distributions in the examples below
    
    poisson_random_variates = poisson.rvs(mu=val1, size=val2)

**Binomial distribution**:

    binom_random_variates = binom.rvs(n=val1, p=prob, size=val2)

**Normal distribution**:

    norm_random_variates = norm.rvs(loc=val1, scale=val2, size=val3)


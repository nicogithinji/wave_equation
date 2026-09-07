# Wave Equation — Task 3.9.1

## Description

This project implements a numerical representation of the solution to the one-dimensional wave equation using a Fourier series.

The solution is expressed as the superposition of two traveling waves:

$$
u(x,t) = f(x-ct) + f(x+ct)
$$

where $f(x-ct)\$ represents a wave traveling to the right and \(f(x+ct)\) represents a wave traveling to the left.

The objective of this task is to evaluate and visualize the displacement of the string at different time values.

## Mathematical Formulation

The solution is constructed using a Fourier sine series:

$$
u(x,t)=\frac{1}{2}\sum_{n=1}^{N}a_n
\left[
\sin(\lambda_n(x-ct))+
\sin(\lambda_n(x+ct))
\right]
$$

where

$$
\lambda_n = \frac{n\pi}{a}
$$

and the Fourier coefficients are given by

$$
a_n =
\sin\left(\frac{n\pi}{2}\right)
\frac{8h}{a^2\lambda_n^2}.
$$

In the numerical implementation, the series is truncated after 9 terms.

## Parameters

The following parameters are used in the simulation:

* **Wave speed:**$c=\sqrt{10^5}\$
* **String length:** $a=1$
* **Initial height:** $h=1$
* **Number of Fourier terms:** 5
* **Spatial points:** 100

The solution is evaluated at the following dimensionless time values:

$$
t = 0,\quad 0.3\frac{a}{c},\quad
0.5\frac{a}{c},\quad
0.7\frac{a}{c},\quad
\frac{a}{c}.
$$

## Implementation

The code is organized into three main components:

### Fourier coefficients

The functions `lambda_n(n)` and `a_n(n)` calculate the eigenvalues and Fourier coefficients, respectively.

### Wave solution

The function `u(x,t)` evaluates the complete wave solution by adding the right- and left-traveling components.

Two additional functions are included:

* `f1(x,t)` — right-traveling wave $f(x-ct)$
* `f2(x,t)` — left-traveling wave $f(x+ct)$

These functions can be plotted separately by uncommenting the corresponding plotting commands.

### Visualization

The displacement \(u(x,t)\) is evaluated at 100 spatial points between \(0\) and \(a\). The resulting wave profiles are plotted for several time values to visualize the evolution of the string.

## Libraries

The following Python libraries are used:

* [NumPy](https://numpy.org/) — numerical calculations and array manipulation
* [Matplotlib](https://matplotlib.org/) — plotting and visualization
* [Pandas](https://pandas.pydata.org/) — data handling
* [SciPy](https://scipy.org/) — scientific computing
* `math` — mathematical functions

## Results

The resulting plots show the displacement of the string at different times. The solution can be interpreted as the superposition of two waves traveling in opposite directions.

By plotting `f1(x,t)` and `f2(x,t)` separately, the individual traveling-wave components can also be visualized.

## How to Run

1. Make sure Python is installed.
2. Install the required libraries if necessary:

```bash
pip install numpy matplotlib pandas scipy
```

3. Run the Python script or execute the notebook cells.
4. The program will generate the wave profiles for the selected time values.

## Author

Nicol Bermejo

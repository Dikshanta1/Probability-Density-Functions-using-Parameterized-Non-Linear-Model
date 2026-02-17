# Learn Probability Density Functions using Roll Number Parameterized Non Linear Model

## Project Overview

This project implements a non linear transformation on air quality data
and estimates the parameters of a probability density function based on
the transformed data. The objective is to understand how transformation
and statistical estimation work together in probabilistic modeling.

The workflow includes:

-   Data loading and preprocessing
-   Roll number based non linear transformation
-   Parameter estimation using statistical methods
-   Construction of a Gaussian type probability density function

------------------------------------------------------------------------

## Dataset Information

-   Dataset: India Air Quality Data
-   Feature Used: NO2
-   File Name: mydata.csv
-   Platform: Google Colab
-   Language: Python

The dataset was loaded from Google Drive into Google Colab for
processing.

------------------------------------------------------------------------

## Mathematical Formulation

### Transformation Function

Each value x from the NO2 feature is transformed into z using:

z = x + ar \* arcsin(br \* x)

Where:

ar = 0.05 \* (r mod 7)\
br = 0.3 \* (r mod 5 + 1)

r represents the university roll number.

For roll number 102303201:

r mod 7 = 4\
r mod 5 = 1

Therefore:

ar = 0.20\
br = 0.60

------------------------------------------------------------------------

### Probability Density Function

After transformation, the following probability density function is
learned:

p(z) = c \* exp(-lambda \* (z - mu)\^2)

Where:

mu = mean of transformed values\
variance = variance of transformed values\
lambda = 1 / (2 \* variance)\
c = sqrt(lambda / pi)

This represents a Gaussian shaped density function.

------------------------------------------------------------------------

## Implementation Steps

1.  Mount Google Drive in Colab
2.  Load mydata.csv using pandas
3.  Extract NO2 column and remove missing values
4.  Apply roll number based non linear transformation
5.  Compute mean and variance of transformed data
6.  Estimate lambda, mu and c
7.  Output the learned parameters

------------------------------------------------------------------------

## Technologies Used

-   Python
-   pandas
-   numpy
-   math
-   Google Colab

------------------------------------------------------------------------

## Results

The output of this project consists of the learned parameters:

-   lambda
-   mu
-   c

These parameters define the final probability density function based on
the transformed NO2 data.

------------------------------------------------------------------------

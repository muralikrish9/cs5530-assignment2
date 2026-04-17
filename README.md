# CS 5530 - Assignment 2

Two notebooks, one for each question.

## Setup




## Q1: Used cars data preparation (20 pts)

`q1/analysis.ipynb` walks through cleaning the used-car dataset.

- **(a)** `New_Price` is missing in 86% of rows so it is dropped. `Mileage`, `Engine`, `Power`, `Seats` are missing in under 1% of rows and are imputed (median for the continuous specs, mode for seats).
- **(b)** Units stripped from `Mileage` (kmpl), `Engine` (CC), and `Power` (bhp) by keeping the first whitespace token and parsing as float.
- **(c)** `Fuel_Type` and `Transmission` one-hot encoded with `pd.get_dummies(dtype=int)`.
- **(d)** Added `Car_Age = 2019 - Year` as a new feature.
- **(e)** The six dplyr verbs (select, filter, rename, mutate, arrange, summarize + group_by) run in sequence.

Cleaned output: `q1/data/used_cars_clean.csv`.

## Q2: Sampling and bootstrap on diabetes data (20 pts)

`q2/analysis.ipynb`. Population is the full 768-row file.

- **(a)** Random sample of 25 (seed 42). Sample mean Glucose tracks the population; sample max is lower, which is expected for a small sample.
- **(b)** 98th percentile of BMI. With n=25 this is effectively the top observation, so it swings around the population value.
- **(c)** 500 bootstrap samples of size 150. Average of bootstrap means and standard deviations are very close to the population values; the 98th percentile is noisier but still centered near the population value.

Figures saved to `q2/figures/`.

## Data

Downloaded from the assignment Box links into `q1/data/used_cars.csv` and `q2/data/diabetes.csv`.

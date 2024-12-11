
# Bayesian Spatio-Temporal Modeling of Brazilian Fire Spots

This repository presents an analysis and Bayesian spatio-temporal modeling of wildfire occurrences in Brazil, focusing on their relationship with meteorological factors and land-use transitions. The study investigates over a decade of fire data to assess patterns, identify influencing factors, and evaluate model performance.

---

## Overview

### Motivation
- **Wildfires**: Critical environmental issue, exacerbated by climate change.
- **Region**: Brazil, especially Amazonia, home to 60% of the world’s largest rainforest, vital biodiversity, and significant freshwater reserves.
- **Objective**: Use Bayesian frameworks to model fire spots over time and space, incorporating meteorological and anthropogenic factors.

### Data Sources
1. **Fire Spot Data**: Brazilian National Institute for Space Research (INPE), satellite imagery (2011–2022).
2. **Meteorological Data**: Brazilian National Institute of Meteorology (INMET), hourly data (2012–2021).
3. **Land Use Data**: MapBiomas, annual land-use and transitions data (2011–2021).

### Key Features
- 22 million fire spots analyzed over 12 years.
- Focus on 558 municipalities with detailed meteorological and land-use data.

---

## Data and Methods

### Data Characteristics
- **Variables**:
  - Fire counts per municipality per month.
  - Meteorological: Precipitation, temperature, humidity, radiation, wind speed.
  - Anthropogenic: Land-use transitions (e.g., deforestation, agriculture).
- **Size**: 66960 rows (monthly observations) and 9 columns, representing a spatio-temporal dataset.

### Data Cleaning
- Aggregation: Monthly summaries for fire counts and meteorological data.
- Missing Data: Interpolated meteorological values and imputed land-use transitions.
- Challenges: Summarization, coarseness of MODIS resolution, and data imputation.

### Bayesian Model
- **Goal**: Predict fire spot counts using:
  - Meteorological factors (e.g., precipitation, temperature).
  - Land-use transitions.
- **Structure**: Spatio-temporal generalized linear mixed model.
- **Implementation**: Code written in JAX for performance optimization.
- **Likelihood**: Poisson-distributed fire counts.

---

## Model Performance

### Evaluation Metrics
- Deviance Information Criterion (DIC) for model comparison.
- Chi-squared goodness-of-fit for assessing model accuracy.

### Key Results
- **Small Model**: Log-likelihood: -25,457,027.72, DIC: 1,304,898.
- **Big Model**: Log-likelihood: -728,709.882, DIC: 1,459,754.219.

### Visualization
- Corner plots of posterior distributions.
- Comparative analysis between models.

---

## Installation and Usage

### Prerequisites
- Python 3.8+
- JAX for model computation
- Required Python libraries (see `requirements.txt`)

### Installation
```bash
git clone https://github.com/<your-repo>/wildfire-model.git
cd wildfire-model
pip install -r requirements.txt
```

### Running the Model
To train and evaluate the Bayesian model:
1. Prepare the dataset.
2. Execute `main.py` with appropriate arguments for the small or big model.

---

## Contributors
- **Jan Fritz**: [jfritz@student.ethz.ch](mailto:jfritz@student.ethz.ch)
- **Niklas Viebig**: [nviebig@student.ethz.ch](mailto:nviebig@student.ethz.ch)
- **Luca Titze**: [ltitze@student.ethz.ch](mailto:ltitze@student.ethz.ch)
- **Victor Windhab**: [vwindhab@student.ethz.ch](mailto:vwindhab@student.ethz.ch)

---

## References
This project builds upon the work by:
- Jonatha Sousa Pimentel, Rodrigo S. Bulhões, Paulo Canas Rodrigues.

---

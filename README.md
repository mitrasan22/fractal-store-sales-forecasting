## Store Sales Forecasting with Fractal Method

### Overview
This project leverages fractal-based forecasting techniques to predict store sales. By combining wavelet decomposition, chaos theory, multifractal analysis, and advanced calibration methods, the approach aims to provide accurate and interpretable forecasts for individual stores and aggregate totals.

### Key Fractal Approaches

#### 1. Wavelet Decomposition
- Decomposes time series into components of different frequency bands using wavelets (e.g., Daubechies wavelets).
- Each component is forecasted individually, considering its unique dynamics.

#### 2. Fractal and Chaos Analysis
- **Hurst Exponent**: Measures long-memory or persistence in time series.
- **Lyapunov Exponent**: Estimates chaos by analyzing the divergence of nearby trajectories in the reconstructed state space.
- **Multifractal Detrended Fluctuation Analysis (MFDFA)**: Identifies long-memory or smooth behavior in components.

#### 3. Forecasting Techniques
- **Local Nonlinear Attractor Forecasting**: Uses nearest neighbors in the reconstructed state space to predict future values.
- **ARIMA**: Applied to components with smooth or linear behavior.
- **Exponential Triple Smoothing (ETS)**: Forecasts aggregate totals with weekly seasonality.

#### 4. Calibration and Optimization
- **NNLS Calibration**: Ensures per-store forecasts align with aggregate totals using non-negative least squares.
- **Cluster-Level Ridge Regression**: Groups similar stores and optimizes allocations using regularized closed-form solutions.

#### 5. Recursive Forecasting
- Predicts day-by-day for the test horizon, incorporating autoregressive updates and known covariates.

#### 6. Fractional Differencing
- Stabilizes memory in time series without completely removing low-frequency structures.

## Files
- `fractal_store_sales_forecasting.ipynb`: The main notebook for sales forecasting. It includes:
  - **Fractal Approaches**:
    - **Wavelet-Based Fractal Forecasting**:
      - Decomposes each store's time series into wavelet components.
      - Predicts each component using fractal/chaos predictors (e.g., Hurst exponent, embedding, local nearest neighbors).
      - Combines component forecasts into per-store shapes and calibrates them to match aggregate forecasts using NNLS.
      - Uses Exponential Triple Smoothing (ETS) for robust aggregate forecasting.
      - Achieves a MAPE of ~5.2% with cluster-level regularization and ridge regression for calibration.
    - **ARIMA-Enhanced Fractal Forecasting**:
      - Decomposes time series into wavelet components and analyzes their multifractal properties (e.g., Hurst exponent, Lyapunov estimate).
      - Applies ARIMA(1,0,1) to smooth components and local nonlinear attractor forecasting to chaotic components.
      - Combines component forecasts into per-store predictions and calibrates them to match aggregate forecasts.
      - Optimizes fractional differencing to handle long-range dependencies without losing low-frequency structure.
  - **Process Flow**:
    - Data preprocessing.
    - Baseline models using Exponential Smoothing.
    - Deep learning models (LSTM) with recursive forecasting.
    - Fractal-based forecasting leveraging chaos theory and multifractal analysis.
    - Evaluation using metrics like MAE, RMSE, and MAPE.
  - **Results**:
    - Tuned fractal approaches outperform other methods, achieving high accuracy and robustness.
- `LICENSE`: MIT License, authored by Santanu Mitra.
- `README.md`: This file, providing an overview of the project.

## Requirements
To run the notebook, ensure you have the following installed:
- Python 3.10+
- Jupyter Notebook
- Required Python libraries (see the notebook for details)

## Usage
1. Open the Jupyter Notebook `fractal_store_sales_forecasting.ipynb`.
2. Follow the instructions in the notebook to preprocess data, train models, and evaluate results.

### Evaluation Metrics
The following metrics are used to assess model performance:
- **Mean Absolute Error (MAE)**
- **Root Mean Squared Error (RMSE)**
- **Mean Absolute Percentage Error (MAPE)**

### Results
- The tuned fractal approach achieved excellent results, with a MAPE of approximately 5.2%.
- Further optimization and exploration of fractal methods are planned for future work.

### License
This project is licensed under the MIT License.

### Author
Santanu Mitra
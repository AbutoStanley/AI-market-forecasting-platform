**AI Stock Forecasting System**

A machine learning system for forecasting stock prices using an ensemble of deep learning and gradient boosting models.
The system combines multiple architectures to capture different patterns in financial time-series data and produces multi-day forecasts with confidence estimates.

**Overview**

Financial markets are noisy and highly nonlinear. Instead of relying on a single model, this project uses an ensemble approach that combines:

- Transformer networks for capturing long-range temporal patterns
- LSTM networks for sequential memory
- XGBoost for nonlinear tabular relationships

The ensemble improves prediction stability and reduces model bias.

The system predicts 7-day future price movements and includes directional confidence scores that decrease as the forecast horizon increases.

**Features**
Multi-model ensemble forecasting
7-day prediction horizon
Time-series cross-validation
Directional accuracy scoring
Confidence decay based on prediction horizon
Feature engineering for financial indicators
Modular training pipeline
UI support for real-time visualization of model predictions
Model Architecture

The system combines three models:

**Transformer**

Captures long-range dependencies and complex market patterns.

**LSTM**

Learns sequential price dynamics and short-term memory effects.

**XGBoost**

Handles nonlinear relationships between engineered features.

The final prediction is generated through ensemble averaging across models.

**Dataset Features**
Example input features include:

- Open
- High
- Low
- Close
- Volume
- Technical indicators
- Lagged features
- Rolling statistics

Data is converted into time-window sequences before being fed into the neural models.

**Training**

Training uses time-series cross validation to prevent data leakage.

Example:

python -m backend.app.training.train

The pipeline:

1. Load and preprocess market data
2. Create time-window sequences
3. Train models across folds
4. Evaluate validation performance
5. Save trained models

**Evaluation Metrics**
Models are evaluated using:
-Mean Squared Error (MSE)
-Directional Accuracy
-Ensemble performance across folds

**Future Improvements**
Planned enhancements include:
-Real-time prediction dashboard
-Interactive visualization of model predictions
-Feature importance analysis
-Reinforcement learning trading strategy
-Live market data integration

**Technologies Used**
-Python
-PyTorch
-XGBoost
-NumPy
-Pandas
-FastAPI (planned)
-React (for visualization dashboard)

**Disclaimer**
This project is for research and educational purposes only.
It is not financial advice and should not be used as the sole basis for trading decisions.

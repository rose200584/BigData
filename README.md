# Financial Fraud Analytics

A Streamlit dashboard and Python analysis pipeline for exploring financial news sentiment, financial keywords, credit-card fraud predictions, and transaction anomalies.

## Dashboard

The dashboard reads the generated CSV files in `outputs\`. Those files are included in this repository, so you can launch the dashboard without retraining the models:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
streamlit run app.py
```

## Analysis scripts

The scripts in `src\` preprocess data, train models, and generate reports in `outputs\` and models in `models\`. Run them from the repository root in this order:

```powershell
python src\news_preprocessing.py
python src\news_classification.py
python src\news_category_classification.py
python src\keyword_extraction.py
python src\transaction_preprocessing.py
python src\fraud_detection.py
python src\isolation_forest.py
python src\pattern_discovery.py
```

The transaction scripts expect `datasets\creditcard.csv`, which is not included in the repository. Place a compatible dataset there before running those scripts. The news preprocessing script uses the included `datasets\Sentences_AllAgree.txt`.

## Project layout

- `app.py` - Streamlit dashboard
- `src\` - preprocessing, classification, fraud detection, and analysis scripts
- `datasets\` - input data
- `models\` - saved model files
- `outputs\` - generated data, metrics, and charts

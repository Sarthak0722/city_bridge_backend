# 🚀 crediscore

[![FastAPI](https://img.shields.io/badge/FastAPI-005571?logo=fastapi&logoColor=white)](https://fastapi.tiangolo.com/) [![MongoDB](https://img.shields.io/badge/MongoDB-4EA94B?logo=mongodb&logoColor=white)](https://www.mongodb.com/) [![Python](https://img.shields.io/badge/Python-3.8%2B-blue?logo=python&logoColor=white)](https://www.python.org/) [![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

> **AI-powered Business Credit Scoring API**

Empower your fintech solutions with real-time, AI-driven business credit scores. crediscore leverages machine learning and modern APIs to deliver fast, reliable, and insightful credit analytics for businesses of all sizes.

---

## ✨ Features

- 🤖 **AI-Powered Scoring**: Predict business credit scores using a trained ML model
- 📊 **Historical Tracking**: Store and retrieve business credit score history
- ⚡ **Blazing Fast API**: Built with FastAPI for high performance
- 🗄️ **MongoDB Integration**: Persistent, scalable data storage
- 🌐 **CORS Enabled**: Ready for frontend and cross-origin integrations

---

## 🗂️ Project Structure

```
api/           # FastAPI app and entry point
routes/        # API route definitions
models/        # Pydantic models and database connection
ml/            # Machine learning model and utilities
```

---

## 🚦 Getting Started

### 1. Clone the Repository
```bash
git clone <repo-url>
cd FinScoreX_Backend-main
```

### 2. Install Dependencies
```bash
pip install -r requirements.txt
```

### 3. Configure Environment Variables
Create a `.env` file in the root directory:
```env
MONGO_URI=mongodb://<username>:<password>@<host>:<port>/<database>
```

### 4. Run the Application
```bash
# Using app.py
python app.py

# Or with uvicorn
uvicorn api.main:app --host 0.0.0.0 --port 7860 --reload
```

The API will be live at: [http://localhost:7860/](http://localhost:7860/)

---

## 📚 API Documentation

### 🩺 Health Check
- **GET /**
  - _Returns:_ `{ "message": "CIBIL Score API is running!" }`

### 📝 Calculate Business Credit Score
- **POST /calculate/**
  - _Description:_ Submit business data to calculate and store a credit score.
  - _Request Body Example:_
    ```json
    {
      "Business_ID": "BIZ123",
      "Business_Type": "Retail",
      "Industry_Sector": "Consumer Goods",
      "Years_in_Operation": 5,
      "Monthly_Revenue": 100000.0,
      "Monthly_Expenses": 80000.0,
      "Loan_Repayment_History": "Early Payment",
      "Outstanding_Debt": 20000.0,
      "Cash_Flow_Stability_Score": 0.8,
      "GST_Filings": 12,
      "Supplier_Payment_Delay": 2,
      "Ecommerce_Sales_Volume": 50000.0,
      "Digital_Invoice_Payment_Rate": 0.9,
      "Credit_Default_History": 0,
      "Business_Growth_Rate": 0.15,
      "Macroeconomic_Risk_Score": 0.3,
      "Social_Media_Sentiment": 0.7,
      "Regulatory_Compliance_Score": 0.95,
      "Month": "2024-06"
    }
    ```
  - _Response Example:_
    ```json
    {
      "message": "Score calculated and stored successfully.",
      "Business_ID": "BIZ123",
      "AI_Credit_Score": 750.0
    }
    ```

### 📈 Get CIBIL Scores
- **GET /cibil/**
  - _Description:_ Retrieve all stored business credit scores and their history.
  - _Response Example:_
    ```json
    {
      "months": ["2024-05", "2024-06"],
      "data": [
        {
          "_id": "...",
          "businessId": "BIZ123",
          "businessType": "Retail",
          "industrySector": "Consumer Goods",
          "month": "2024-06",
          "date": "2024-06-15",
          "score": 750.0,
          "previousScore": 740.0
        }
      ]
    }
    ```

---

## ⚙️ Environment Variables

| Variable    | Description                  | Required |
|-------------|------------------------------|----------|
| `MONGO_URI` | MongoDB connection string    |   ✅     |

---

## 🧩 Dependencies

- [FastAPI](https://fastapi.tiangolo.com/)
- [Uvicorn](https://www.uvicorn.org/)
- [Motor](https://motor.readthedocs.io/en/stable/)
- [NumPy](https://numpy.org/)
- [scikit-learn](https://scikit-learn.org/)
- [joblib](https://joblib.readthedocs.io/en/latest/)
- [python-dotenv](https://pypi.org/project/python-dotenv/)
- [pydantic](https://docs.pydantic.dev/)

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome!<br>
Feel free to check the [issues page](../../issues) or submit a pull request.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

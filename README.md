# 🚗 Car Price Prediction with Machine Learning

![Car-Price-Prediction-Streamlit](image.jpg)

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.40.2-FF4B4B.svg)](https://streamlit.io/)
[![scikit-learn](https://img.shields.io/badge/scikit--learn-1.5.2-F7931E.svg)](https://scikit-learn.org/)
[![License](https://img.shields.io/badge/License-Apache%202.0-green.svg)](LICENSE)

## 📋 Table of Contents
- [Overview](#overview)
- [Features](#features)
- [Dataset](#dataset)
- [Technologies Used](#technologies-used)
- [Project Structure](#project-structure)
- [Installation](#installation)
- [Usage](#usage)
- [Model Architecture](#model-architecture)
- [Results](#results)
- [Deployment](#deployment)
- [Contributing](#contributing)
- [License](#license)
- [Contact](#contact)

## 🎯 Overview

This project implements an end-to-end machine learning solution for predicting used car prices based on various features such as brand, age, fuel type, transmission, and more. The project includes comprehensive data analysis, model training with Random Forest algorithm, and an interactive web application built with Streamlit for real-time price predictions.

**Key Highlights:**
- 📊 Analyzed **4,340+ car records** from CarDekho dataset
- 🤖 Built and trained a **Random Forest Regressor** model
- 🎨 Deployed an interactive **Streamlit** web application
- 📦 Implemented production-ready ML pipeline with preprocessing
- 🎯 Achieved high prediction accuracy with proper feature engineering

## ✨ Features

### Machine Learning Pipeline
- **Advanced Preprocessing**: Utilizes `ColumnTransformer` and `Pipeline` for efficient data transformation
- **Feature Engineering**: 
  - One-Hot Encoding for categorical variables (fuel type, seller type, transmission, owner type, car brand)
  - Standard Scaling for numerical features (kilometers driven, car age)
  - Age calculation from manufacturing year
- **Random Forest Model**: Trained ensemble model with 20 estimators for accurate and reliable predictions
- **Model Persistence**: Serialized model using `pickle` for quick deployment and inference

### Web Application
- **Interactive UI**: User-friendly Streamlit interface for inputting car details
- **Real-time Predictions**: Instant price estimation based on user inputs
- **Input Validation**: Smart input controls with appropriate ranges and options
- **Dynamic Features**: 
  - Automatic age calculation from manufacturing year
  - Support for 29 car brands
  - Multiple fuel types (Petrol, Diesel, CNG, LPG, Electric)
  - Various owner types and seller categories

### Data Analysis
- **Exploratory Data Analysis (EDA)**: Comprehensive analysis in Jupyter notebooks
- **Data Visualization**: Plots and charts for understanding data distribution
- **Missing Value Handling**: Clean dataset preparation
- **Statistical Analysis**: Descriptive statistics and correlation analysis

## 📊 Dataset

**Source**: CAR DETAILS FROM CAR DEKHO.csv

**Dataset Statistics:**
- **Total Records**: 4,340 cars
- **Features**: 8 columns

**Features Description:**
| Feature | Type | Description |
|---------|------|-------------|
| `name` | String | Full name/model of the car |
| `year` | Integer | Manufacturing year of the car |
| `selling_price` | Integer | Selling price in INR (Target Variable) |
| `km_driven` | Integer | Total kilometers driven |
| `fuel` | Categorical | Fuel type (Petrol, Diesel, CNG, LPG, Electric) |
| `seller_type` | Categorical | Type of seller (Individual, Dealer, Trustmark Dealer) |
| `transmission` | Categorical | Transmission type (Manual, Automatic) |
| `owner` | Categorical | Ownership history (First Owner, Second Owner, etc.) |

**Supported Car Brands** (29 brands):
Maruti, Hyundai, Datsun, Honda, Tata, Chevrolet, Toyota, Jaguar, Mercedes-Benz, Audi, Skoda, Jeep, BMW, Mahindra, Ford, Nissan, Renault, Fiat, Volkswagen, Volvo, Mitsubishi, Land Rover, Daewoo, MG, Force, Isuzu, OpelCorsa, Ambassador, Kia

## 🛠️ Technologies Used

### Core Technologies
- **Python 3.8+**: Primary programming language
- **Jupyter Notebook**: For data analysis and model development
- **Streamlit 1.40.2**: Web application framework

### Machine Learning & Data Science
- **scikit-learn 1.5.2**: Machine learning algorithms and preprocessing
- **pandas 2.2.3**: Data manipulation and analysis
- **numpy 2.1.3**: Numerical computing
- **matplotlib**: Data visualization

### Model Components
- **RandomForestRegressor**: Ensemble learning algorithm
- **ColumnTransformer**: Feature preprocessing
- **Pipeline**: ML workflow automation
- **OneHotEncoder**: Categorical feature encoding
- **StandardScaler**: Feature scaling

### Deployment & Utilities
- **pickle**: Model serialization
- **datetime**: Date/time operations for age calculation

## 📁 Project Structure

```
car-price-prediction/
│
├── 📓 Car_Price_Prediction1.ipynb          # Initial model development notebook
├── 📓 Car_Price_Prediction1_Streamlit.ipynb # Streamlit pipeline development notebook
├── 🐍 car_price_streamlit.py               # Streamlit web application
├── 📊 CAR DETAILS FROM CAR DEKHO.csv       # Dataset file
├── 🤖 predict_car_price.pkl                # Trained model pipeline (serialized)
├── 🖼️ image.jpg                            # Project banner image
├── 📋 requirements.txt                     # Python dependencies
├── 📄 README.md                            # Project documentation
├── 📜 LICENSE                              # Apache 2.0 License
└── 🚫 .gitignore                           # Git ignore rules
```

## 🚀 Installation

### Prerequisites
- Python 3.8 or higher
- pip package manager
- Git (for cloning the repository)

### Step 1: Clone the Repository
```bash
git clone https://github.com/arpanpramanik2003/car-price-prediction.git
cd car-price-prediction
```

### Step 2: Create Virtual Environment (Recommended)
```bash
# On Windows
python -m venv venv
venv\Scripts\activate

# On macOS/Linux
python3 -m venv venv
source venv/bin/activate
```

### Step 3: Install Dependencies
```bash
pip install -r requirements.txt
```

**Note**: The `requirements.txt` file includes all necessary packages:
- streamlit==1.40.2
- pandas==2.2.3
- numpy==2.1.3
- scikit-learn==1.5.2
- And other supporting libraries

## 💻 Usage

### Running the Streamlit Web Application

1. **Start the Streamlit server**:
```bash
streamlit run car_price_streamlit.py
```

2. **Access the application**:
   - Open your web browser
   - Navigate to `http://localhost:8501`

3. **Make Predictions**:
   - Select the car brand from dropdown
   - Enter kilometers driven
   - Choose manufacturing year
   - Select fuel type
   - Choose seller type
   - Select transmission type
   - Choose owner type
   - Click "Predict Selling Price" button
   - View the estimated price in INR (₹)

### Working with Jupyter Notebooks

#### Option 1: Model Training from Scratch
```bash
jupyter notebook Car_Price_Prediction1.ipynb
```
This notebook covers:
- Data loading and exploration
- Exploratory Data Analysis (EDA)
- Data preprocessing and encoding
- Feature engineering (Age calculation)
- Model training with Random Forest
- Model evaluation on training and test data

#### Option 2: Streamlit Pipeline Development
```bash
jupyter notebook Car_Price_Prediction1_Streamlit.ipynb
```
This notebook includes:
- Data preprocessing with ColumnTransformer
- Pipeline creation with OneHotEncoder and StandardScaler
- Random Forest model training
- Model serialization with pickle
- Preparation for Streamlit deployment

## 🏗️ Model Architecture

### Preprocessing Pipeline

```python
ColumnTransformer:
  ├── OneHotEncoder (drop='first')
  │   └── Features: ['fuel', 'seller_type', 'transmission', 'owner', 'car_brand']
  └── StandardScaler
      └── Features: ['km_driven', 'age']
```

### Model Configuration

- **Algorithm**: Random Forest Regressor
- **Number of Estimators**: 20 trees
- **Random State**: 2 (for reproducibility)
- **Target Variable**: Selling Price (INR)

### Training Process

1. **Data Loading**: Import CAR DEKHO dataset
2. **Feature Engineering**: 
   - Extract car brand from car name
   - Calculate car age from manufacturing year
3. **Data Splitting**: 80-20 train-test split
4. **Pipeline Training**: 
   - Categorical encoding with OneHotEncoder
   - Numerical scaling with StandardScaler
   - Model training with Random Forest
5. **Model Serialization**: Save pipeline as `predict_car_price.pkl`

### Model Workflow

```
User Input → Preprocessing Pipeline → Random Forest Model → Price Prediction
              (Encoding + Scaling)      (20 Estimators)
```

## 📈 Results

The Random Forest model was evaluated using R² score metrics:

- **Training Performance**: High R² score indicating good fit on training data
- **Test Performance**: Consistent performance on unseen test data
- **Model Reliability**: Ensemble approach reduces overfitting

**Key Achievements**:
- ✅ Successfully handles 29 different car brands
- ✅ Processes multiple categorical and numerical features
- ✅ Provides real-time predictions through web interface
- ✅ Production-ready ML pipeline with proper preprocessing

## 🌐 Deployment

### Local Deployment
The application runs locally using Streamlit. Follow the [Usage](#usage) section to start the server.

### Cloud Deployment Options

#### Streamlit Cloud (Recommended)
1. Push your code to GitHub
2. Visit [share.streamlit.io](https://share.streamlit.io)
3. Connect your GitHub repository
4. Deploy with one click

#### Other Platforms
- **Heroku**: Deploy with Procfile configuration
- **AWS EC2**: Deploy on cloud server
- **Google Cloud Platform**: Use App Engine or Cloud Run
- **Azure**: Deploy as Web App

**Important Files for Deployment**:
- `requirements.txt`: Python dependencies
- `car_price_streamlit.py`: Main application file
- `predict_car_price.pkl`: Pre-trained model (11MB+)
- `CAR DETAILS FROM CAR DEKHO.csv`: Dataset (if needed)

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Fork the repository**
2. **Create a feature branch**:
   ```bash
   git checkout -b feature/YourFeatureName
   ```
3. **Make your changes**
4. **Commit your changes**:
   ```bash
   git commit -m "Add some feature"
   ```
5. **Push to the branch**:
   ```bash
   git push origin feature/YourFeatureName
   ```
6. **Open a Pull Request**

### Areas for Contribution
- 🐛 Bug fixes and issue resolution
- ✨ New features (e.g., more ML models, visualizations)
- 📝 Documentation improvements
- 🎨 UI/UX enhancements
- 🧪 Additional test cases
- 📊 More comprehensive data analysis

## 📄 License

This project is licensed under the **Apache License 2.0** - see the [LICENSE](LICENSE) file for details.

```
Copyright 2024 Arpan Pramanik

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

    http://www.apache.org/licenses/LICENSE-2.0
```

## 👤 Contact

**Arpan Pramanik**

- 🐱 GitHub: [@arpanpramanik2003](https://github.com/arpanpramanik2003)
- 📧 Email: [Contact via GitHub](https://github.com/arpanpramanik2003)
- 💼 Project Link: [https://github.com/arpanpramanik2003/car-price-prediction](https://github.com/arpanpramanik2003/car-price-prediction)

---

<div align="center">

### ⭐ Star this repository if you find it helpful!

**Made with ❤️ by Arpan Pramanik**

</div>

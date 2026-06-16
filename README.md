# 📰 FactCheck - AI Fake News Detection System

## 🎯 Live Demo

> **Try it now:** [**factcheck-phkj.onrender.com**](https://factcheck-phkj.onrender.com/)

[![Live Demo](https://img.shields.io/badge/LIVE_DEMO-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://factcheck-phkj.onrender.com/)
[![Python](https://img.shields.io/badge/Python-3.8+-3776AB?style=for-the-badge&logo=python&logoColor=white)](https://www.python.org/)
[![Scikit-Learn](https://img.shields.io/badge/Scikit--Learn-1.0+-F7931E?style=for-the-badge&logo=scikit-learn&logoColor=white)](https://scikit-learn.org/)
[![Streamlit](https://img.shields.io/badge/Streamlit-1.0+-FF4B4B?style=for-the-badge&logo=streamlit&logoColor=white)](https://streamlit.io/)
[![Render](https://img.shields.io/badge/Deployed-Render-46E3B7?style=for-the-badge&logo=render&logoColor=white)](https://render.com/)
[![License](https://img.shields.io/badge/License-MIT-blue.svg?style=for-the-badge)](LICENSE)

---

## 📋 Overview

**FactCheck** is an AI-powered fake news detection system that uses machine learning to analyze news articles and determine their authenticity with **95.8% accuracy**. Built with a robust NLP pipeline and deployed as an interactive web application, it provides real-time predictions with confidence scoring.

### 🏆 Key Achievements

- ✅ **95.8% Test Accuracy** on 18,017 unique news articles
- ✅ **0.992 ROC-AUC** demonstrating excellent discrimination capability
- ✅ **2.2% Train-Test Gap** - no overfitting
- ✅ **5-fold Stratified Cross-Validation** ensuring model robustness
- ✅ **Production-ready** - Live deployment on Render
- ✅ **User-friendly Interface** - Built with Streamlit

---

## 🚀 Features

### Core Features
- **🔍 Real-time Detection** - Instant classification with confidence scores
- **📊 Confidence Meter** - Visual probability breakdown
- **📝 Multiple Input Methods** - Type text, paste, or try examples
- **📈 Article Analytics** - Word count, capitalization, exclamation analysis
- **🚩 Red Flag Detection** - Identify common fake news patterns
- **💡 Educational Tips** - Learn to spot fake news yourself

### Technical Features
- **🧠 ML Pipeline** - Logistic Regression with TF-IDF vectorization
- **🔬 NLP Processing** - Text cleaning, stopword removal, n-gram analysis
- **📦 Production Ready** - Serialized model for fast inference
- **🎨 Responsive UI** - Works on desktop and mobile
- **⚡ Fast Inference** - < 1 second response time

---

## 📊 Model Performance

### Model Comparison

| Model | Test Accuracy | CV Accuracy | ROC-AUC |
|-------|--------------|-------------|---------|
| **Logistic Regression** | **95.8%** | **95.0%** | **0.992** |
| Random Forest | 91.0% | 91.2% | 0.970 |
| Naive Bayes | 91.1% | 90.3% | 0.976 |

### Classification Report

```
              precision    recall  f1-score   support
   real news       0.97      0.96      0.96      2073
   fake news       0.95      0.95      0.95      1531

    accuracy                           0.96      3604
   macro avg       0.96      0.96      0.96      3604
weighted avg       0.96      0.96      0.96      3604
```

### Confusion Matrix

```
              Predicted
              Real    Fake
Actual Real   1990     83
Actual Fake     77   1454
```

---

## 🛠️ Technology Stack

### Machine Learning
- Scikit-learn (Logistic Regression, Random Forest, Naive Bayes)
- TF-IDF Vectorization with n-grams (1,2)
- 5-fold Stratified Cross-Validation

### NLP Pipeline
- NLTK for stopword removal
- Regex for text cleaning
- Feature engineering (max_features=10,000)

### Web Application
- Streamlit for interactive UI
- Pickle for model serialization
- Render for cloud deployment

### Visualization & Analysis
- Matplotlib & Seaborn for EDA
- Confusion matrix and classification reports
- Interactive confidence meter

---

## 📁 Project Structure

```
FactCheck/
├── dataset/
│   └── train.csv                 # Training data (20,800 articles)
├── FactCheck_models/             # Serialized models
│   ├── fake_news_model.pkl       # Best performing model (LR)
│   └── tfidf_vectorizer.pkl      # TF-IDF vectorizer
├── FactCheck_outputs/            # Visualizations
│   ├── distribution.png          # Class distribution
│   └── confusion_matrix.png      # Model performance
├── app.py                        # Streamlit web application
├── train.py                      # Training pipeline
├── requirements.txt              # Dependencies
└── README.md                     # This file
```

---

## 💻 Installation & Setup

### Prerequisites
```bash
Python 3.8+
pip
```

### Local Development

1. **Clone the repository**
```bash
git clone https://github.com/boughanmiyoussef/factcheck.git
cd factcheck
```

2. **Install dependencies**
```bash
pip install -r requirements.txt
```

3. **Download NLTK stopwords**
```python
python -c "import nltk; nltk.download('stopwords')"
```

4. **Train the model** (optional - model is included)
```bash
python train.py
```

5. **Run the web application**
```bash
streamlit run app.py
```

6. **Open your browser**
```
http://localhost:8501
```

---

## 🔧 Usage Guide

### Using the Web Interface

1. **Choose input method:**
   - ✍️ **Type or paste text** - Enter your own news article
   - 🎯 **Try an example** - Test with pre-loaded examples
   - 🔗 **URL (coming soon)** - Paste a URL for analysis

2. **Click "🔍 Analyze News"**

3. **Review results:**
   - ✅ REAL NEWS or ⚠️ FAKE NEWS
   - Confidence percentage
   - Article statistics
   - Red flags detected
   - Suggestions for verification

### Example News Articles

Try these examples in the app:

**Real News Examples:**
- "The Federal Reserve announced today that interest rates will remain unchanged at 5.25 percent following their quarterly meeting. The decision was expected by economists."
- "Researchers at Stanford University published a study showing that 30 minutes of daily exercise reduces heart disease risk by 25 percent."

**Fake News Examples:**
- "BREAKING: The government is hiding alien technology at Area 51! Whistleblower reveals shocking truth about extraterrestrial contact!"
- "SHOCKING: Doctors don't want you to know that this simple kitchen ingredient cures cancer naturally!"

---

## 🚀 Deployment

### Deploy on Render

1. **Push to GitHub**
2. **Create a new Web Service on Render**
3. **Connect your repository**
4. **Set build command:**
```bash
pip install -r requirements.txt
```

5. **Set start command:**
```bash
streamlit run app.py --server.port=10000
```

6. **Add environment variables:**
```
PYTHON_VERSION = 3.9.0
```

### Deploy on Streamlit Cloud

1. **Push to GitHub**
2. **Go to share.streamlit.io**
3. **Deploy from GitHub repository**

### Docker Deployment

```dockerfile
FROM python:3.9-slim
WORKDIR /app
COPY requirements.txt .
RUN pip install -r requirements.txt
COPY . .
EXPOSE 8501
CMD ["streamlit", "run", "app.py", "--server.port=8501"]
```

---

## 📈 Dataset & Training

### Dataset Statistics
- **Total articles**: 20,800
- **Unique samples**: 18,017 (after deduplication)
- **Class distribution**: ~50% real, ~50% fake
- **Average article length**: 4,329-5,199 characters
- **Features**: Title, Author, Text, Label

### Training Pipeline

```python
1. Data Loading & Cleaning
   ↓
2. Text Preprocessing (Cleaning, Stopwords)
   ↓
3. TF-IDF Vectorization (10,000 features, n-grams 1-2)
   ↓
4. Model Training (Logistic Regression)
   ↓
5. 5-Fold Stratified Cross-Validation
   ↓
6. Model Evaluation & Selection
   ↓
7. Model Serialization & Deployment
```

---

## 🎨 Web App Features

### Interactive Elements
- **🎯 Example Selector** - Pre-loaded real and fake articles
- **📊 Confidence Meter** - Visual probability gauge
- **📈 Article Analytics** - Word count, exclamation marks, capitalization
- **🚩 Red Flag Detection** - Automatic pattern recognition
- **💡 Educational Tips** - Learn to identify fake news
- **📱 Responsive Design** - Works on all devices

### User Experience
- **Instant Results** - < 1 second response time
- **Clear Visuals** - Green for real, red for fake
- **Detailed Analysis** - Expand for more information
- **Actionable Advice** - Specific verification steps

---

## 🔄 Future Improvements

### Planned Features
- [ ] **URL Analysis** - Extract and analyze text from URLs
- [ ] **Deep Learning** - Implement transformers (BERT, RoBERTa)
- [ ] **Multi-language Support** - Detect fake news in multiple languages
- [ ] **Browser Extension** - Chrome/Firefox extension
- [ ] **API Endpoint** - RESTful API for integration
- [ ] **Source Credibility** - Domain authority scoring
- [ ] **Fact-Checking** - Cross-reference with fact-checking databases
- [ ] **Batch Processing** - Analyze multiple articles at once
- [ ] **PDF/Image OCR** - Extract text from images and PDFs
- [ ] **Social Media Integration** - Analyze tweets and posts

### Performance Improvements
- [ ] **Model Explainability** - Add SHAP/LIME for interpretability
- [ ] **A/B Testing** - Compare multiple models in production
- [ ] **Monitoring** - Track model performance over time
- [ ] **Retraining Pipeline** - Automated retraining with new data

---

## 🤝 Contributing

Contributions are welcome! Please follow these steps:

1. **Fork the repository**
2. **Create a feature branch**
```bash
git checkout -b feature/AmazingFeature
```
3. **Commit your changes**
```bash
git commit -m 'Add AmazingFeature'
```
4. **Push to the branch**
```bash
git push origin feature/AmazingFeature
```
5. **Open a Pull Request**

---

## 👨‍💻 Author

**Youssef Boughanmi**
- 🎓 Software Engineer | ML & Full-Stack
- 📧 yussefboughanmy@gmail.com
- 🔗 [LinkedIn](https://linkedin.com/in/youssef-boughanmi-4990222a0)
- 🐙 [GitHub](https://github.com/boughanmiyoussef)
- 🌐 [Portfolio](https://boughanmiyoussef.github.io)

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## 🙏 Acknowledgments

- Dataset: [Kaggle Fake News Dataset](https://www.kaggle.com/c/fake-news)
- Scikit-learn documentation and community
- Holberton School for project guidance
- Streamlit for the amazing framework
- Render for seamless deployment

---

## 📊 Project Stats

[![GitHub stars](https://img.shields.io/github/stars/boughanmiyoussef/factcheck?style=social)](https://github.com/boughanmiyoussef/factcheck)
[![GitHub forks](https://img.shields.io/github/forks/boughanmiyoussef/factcheck?style=social)](https://github.com/boughanmiyoussef/factcheck)
[![GitHub issues](https://img.shields.io/github/issues/boughanmiyoussef/factcheck)](https://github.com/boughanmiyoussef/factcheck/issues)
[![Deployment](https://img.shields.io/badge/Live%20Demo-Online-success)](https://factcheck-phkj.onrender.com/)

---

## 📝 Quick Setup Script

Add this to your `requirements.txt`:

```txt
streamlit==1.28.0
scikit-learn==1.2.2
pandas==2.0.3
numpy==1.24.3
nltk==3.8.1
matplotlib==3.7.2
seaborn==0.12.2
plotly==5.15.0
```

---

## 🔒 Privacy Notice

- **No data storage** - All text is processed in real-time
- **No logging** - We don't save your articles
- **Open source** - Full transparency
- **Encrypted connection** - HTTPS for all requests

---

<div align="center">
  
### ⭐️ If you found this project useful, please give it a star! ⭐️

**Try the live demo:** [**factcheck-phkj.onrender.com**](https://factcheck-phkj.onrender.com/)

**Built with ❤️ by Youssef Boughanmi**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://linkedin.com/in/youssef-boughanmi-4990222a0)
[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/boughanmiyoussef)
[![Email](https://img.shields.io/badge/Email-D14836?style=for-the-badge&logo=gmail&logoColor=white)](mailto:yussefboughanmy@gmail.com)
[![Portfolio](https://img.shields.io/badge/Portfolio-FF5722?style=for-the-badge&logo=google-chrome&logoColor=white)](https://boughanmiyoussef.github.io)

</div>

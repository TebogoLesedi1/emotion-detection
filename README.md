# Emotion Detection & Sentiment Analysis

A comprehensive emotion and sentiment analysis system that detects emotional states (joy, sadness, fear, etc.) and sentiment polarity (positive, negative, neutral) from text. Originally developed to support contextual understanding for chatbots assisting Gender-Based Violence (GBV) survivors.

## 📋 Overview

This project implements a multi-layered NLP pipeline that processes textual input to:
- Detect emotional tones (joy, sadness, fear, anger, etc.)
- Analyze sentiment polarity (positive, negative, neutral)
- Extract contextual themes and topics
- Enable empathetic, context-aware chatbot responses

## 🎯 Problem Statement

Chatbots often fail to understand the emotional tone and context of user messages, leading to robotic or inappropriately timed responses. This is especially critical when supporting vulnerable populations like GBV survivors who need empathetic, contextually-aware interactions.

## ✨ Solution

This project uses a combination of NLP techniques to:
- **Understand emotional context** from user messages
- **Detect sentiment polarity** to gauge user affect
- **Extract topics and themes** to understand underlying concerns
- **Enable contextual responses** that acknowledge user emotions

## 📊 Dataset & Analysis

- **117 text samples** from GBV support testimonials
- **Labeled with emotional states** (joy, sadness, fear, anger, neutral)
- **Sentiment scored** using VADER sentiment analyzer
- **Topics extracted** using Latent Dirichlet Allocation (LDA) modeling

### Key Topics Identified:
- Support systems and community resources
- Legal assistance and protection
- Personal emotional journey and recovery
- Safety and understanding

## 🛠️ Tech Stack

| Component | Technology |
|-----------|-----------|
| **Language** | Python |
| **Data Processing** | Pandas, NumPy |
| **NLP Preprocessing** | NLTK (Tokenization, Stopword Removal, Lemmatization) |
| **Sentiment Analysis** | VADER Sentiment Analyzer |
| **Emotion Detection** | Hugging Face Transformers (`j-hartmann/emotion-english-distilroberta-base`) |
| **Topic Modeling** | Gensim (LDA) |
| **Development** | Jupyter Notebook / Google Colab |

## 📁 Project Structure

```
emotion-detection/
├── README.md                           # This file
├── emotional_support.ipynb            # Main analysis notebook
├── sentiment analysis.png             # Sentiment distribution visualization
├── text analysis.png                  # Text preprocessing visualization
├── the data.png                       # Data overview visualization
```

## 🔄 Pipeline Steps

### 1. **Data Loading**
   - Load testimonial data from CSV
   - Handle missing values

### 2. **Text Preprocessing**
   - Tokenization using NLTK
   - Stopword removal
   - Lemmatization
   - Lowercase conversion

### 3. **Sentiment Analysis**
   - VADER polarity scoring (negative, neutral, positive, compound)
   - Compound score interpretation

### 4. **Emotion Detection**
   - Multi-class emotion classification
   - Batch processing with DistilRoBERTa model
   - Output emotions: joy, sadness, fear, anger, surprise, disgust, neutral

### 5. **Topic Modeling**
   - Create document-term matrix
   - LDA model with 3 topics
   - Extract key themes

### 6. **Model Persistence**
   - Save VADER analyzer to pickle
   - Save DistilRoBERTa emotion model
   - Save LDA topic model

## 📈 Results & Insights

### Sample Predictions:

| Input Text | Emotion | Sentiment |
|-----------|---------|-----------|
| "The support group has been incredibly helpful and supportive" | Joy | Positive |
| "I finally feel safe and understood after joining counseling" | Joy | Positive |
| "I feel betrayed by those who should have protected me" | Sadness | Negative |
| "I am haunted by flashbacks and nightmares" | Fear | Negative |

### Sentiment Distribution
- **Positive**: Support, gratitude, safety, understanding
- **Negative**: Betrayal, trauma, fear, loss
- **Neutral**: Factual descriptions, resource information

## 🚀 Usage

### Basic Setup:
```bash
# Clone the repository
git clone https://github.com/TebogoLesedi1/emotion-detection.git
cd emotion-detection

# Install dependencies
pip install pandas numpy nltk transformers gensim torch

# Download NLTK data
python -c "import nltk; nltk.download('punkt'); nltk.download('stopwords'); nltk.download('wordnet'); nltk.download('vader_lexicon')"
```

### Running the Analysis:
1. Open `emotional_support.ipynb` in Jupyter or Google Colab
2. Mount your data source (if using Google Drive)
3. Run cells sequentially through the pipeline
4. Models are saved for deployment

## 💾 Model Artifacts

The notebook generates three trained model files:
- `vader_sentiment_analyzer.pkl` - Sentiment analysis model
- `emotion_detection_model/` - Emotion classification model
- `lda_model` - Topic modeling

## 🤝 Integration with Phakama AI Chatbot

This pipeline is designed for integration with chatbot systems to:
1. Preprocess user input
2. Detect emotional state
3. Analyze sentiment
4. Generate contextually appropriate responses
5. Provide empathetic support

## 📊 Visualizations

The project includes analysis visualizations:
- **Sentiment Analysis Chart**: Distribution of positive/negative/neutral sentiment
- **Text Analysis Chart**: Preprocessing impact and token distribution
- **Data Overview**: Sample distribution and emotion frequency

## 🔮 Future Enhancements

- [ ] Real-time emotion detection API
- [ ] Fine-tune models on larger GBV-specific datasets
- [ ] Multi-language support
- [ ] Integration with chatbot frameworks (Rasa, Dialogflow)
- [ ] User feedback loop for model improvement
- [ ] Explainability features (LIME/SHAP)
- [ ] Response generation based on detected emotions

## 📚 References

- [NLTK Documentation](https://www.nltk.org/)
- [Hugging Face Transformers](https://huggingface.co/transformers/)
- [VADER Sentiment Analysis](https://github.com/cjhutto/vaderSentiment)
- [Gensim LDA](https://radimrehurek.com/gensim/)

## ⚠️ Important Notes

- **Ethical Consideration**: This model is trained on sensitive GBV survivor testimonials. Use with care and respect for privacy.
- **Model Limitations**: Pre-trained models may not capture all nuances of trauma-informed language
- **Data Privacy**: Ensure compliance with data protection regulations when handling sensitive user data

## 📝 License

[Add your license here - e.g., MIT, Apache 2.0, etc.]

## 👤 Author

**Tebogo Lesedi**
- GitHub: [@TebogoLesedi1](https://github.com/TebogoLesedi1)

## 💬 Contact & Support

For questions or collaboration inquiries, feel free to open an issue or reach out through GitHub.

---

**Last Updated**: 2026-05-06

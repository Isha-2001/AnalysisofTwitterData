# 📱 Social Media Sentiment & Thematic Analysis Dashboard

A real-time Twitter analysis platform designed to help organizations assess customer sentiment and discover major discussion topics about their **mobile phones, laptops, and earphones**. Built with Python and NLP tools, this solution empowers businesses to make informed decisions by monitoring live social media feedback.

---

## 🔍 Problem Statement

In the digital age, customers openly share opinions on platforms like Twitter. Manually tracking and interpreting this feedback is infeasible at scale.

**Objective:**  
Enable companies to:
- Analyze sentiment about their products (e.g., Samsung mobiles)
- Compare performance against competitors
- Detect trending topics and pain points
- React to issues before they escalate

---

## 🛠️ Proposed Method

### 1. 🐦 Data Extraction
- **Source:** Twitter API (via `Tweepy`)
- **Query filters:** Keywords like "Samsung", "mobile", "service"
- **Data size:** 1,000 recent tweets (excluding media content)

---

### 2. 🧹 Data Preprocessing
Clean and prepare tweets for analysis:
- Remove null values, links, and punctuation
- Convert emojis and chat words (e.g., "lol" → "laughing out loud")
- Eliminate stop words
- **Lemmatization:** Convert words to their root forms
- **Tokenization:** Split into word tokens for vectorization

---

### 3. 😃 Sentiment Analysis
Using **TextBlob (nltk)**:
- Label each tweet with:
  - `1`: Positive
  - `0`: Neutral
  - `-1`: Negative
- Adds a `sentiment` column to the dataframe

---

### 4. 📊 Vectorization
Apply **TF-IDF (Term Frequency-Inverse Document Frequency)** to:
- Transform text into numeric features
- Highlight important terms across the tweet corpus

---

### 5. 🧠 Thematic Analysis (Topic Modeling)
**Goal:** Identify dominant discussion topics using:
- **NMF (Non-negative Matrix Factorization)** from `gensim`
- Optimal number of topics selected using **Coherence Score + Elbow Method**

**Output:**
- Topic-to-word and tweet-to-topic matrices
- Topics interpreted using top contributing words

---

### 6. 🧾 Feature Extraction
- Assign each tweet a topic label
- Count positive/neutral/negative tweets per topic
- Create a new dataframe summarizing sentiment per topic

---

## 📈 Results & Visualizations

### ✅ Overall Sentiment Distribution
- Pie chart shows that most tweets are **positive**
- Suggests favorable sentiment around Samsung mobiles

### 📊 Topic vs Sentiment Analysis
- **Bar chart**: Topics on X-axis, tweet count and sentiment colors on Y-axis
  - Topic 2 (Battery & iPhone) is the most discussed
  - Topic 1 (Hardware like screen/glass) has highest positive sentiment
  - Topic 5 (Customer service) is dominated by negative sentiment

### 📋 Topic Sentiment Summary Table
- Table showing:
  - Topic keywords
  - Count of positive, neutral, and negative tweets
- Basis for business insights, comparisons, and dashboards

---

## 📦 Tech Stack

- Python (Pandas, NumPy, NLTK, TextBlob, Gensim, Sklearn)
- Tweepy (Twitter API integration)
- Matplotlib / Seaborn for data visualization

---

## 📌 Applications

- 📉 Brand Monitoring
- 📢 Customer Feedback Analysis
- 🔍 Competitor Benchmarking
- 🔔 Real-Time Issue Detection

---

## 📄 License

This project is under the [MIT License](LICENSE).

---

## 🙌 Acknowledgments

- Twitter API via Tweepy  
- NLP tools: TextBlob, NLTK, Gensim  
- Topic Modeling references from Chirag Goyle and Enes Zvornicanin

---

> 🚀 Want to analyze a different brand or platform? Simply tweak the keyword queries in the `Tweepy` call!

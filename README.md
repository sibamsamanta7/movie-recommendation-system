# 🎬 Movie Recommendation System

A **content-based movie recommender system** that suggests similar movies based on a title you already like — no user rating history required. It uses **TF-IDF vectorization** and **cosine similarity** on each movie's overview, genres, and tagline to find the closest matches.

🔗 **Live Demo:** https://movie-recommendation-system-uvchyhjltnol2me8ggzjua.streamlit.app/

---

## ✨ Features

- Content-based recommendations using **TF-IDF + Cosine Similarity**
- Text preprocessing pipeline (cleaning, stopword removal, lemmatization) with **NLTK**
- **FastAPI** backend serving recommendations via a REST API
- **Streamlit** frontend for an interactive, user-friendly UI
- Pre-trained model artifacts (TF-IDF matrix, vectorizer, and lookup index) saved with `pickle` for fast startup — no retraining needed on every run

---

## 🛠️ Tech Stack

| Layer | Tools |
|---|---|
| Language | Python |
| Data Processing | Pandas, NumPy |
| NLP / ML | scikit-learn (TF-IDF, Cosine Similarity), NLTK |
| Backend API | FastAPI, Uvicorn |
| Frontend | Streamlit |
| Model Persistence | Pickle |

---

## 📂 Project Structure

```
movie-recommendation-system/
│
├── Movie_Recommendation_System.ipynb   # Full notebook: data cleaning → training pipeline
├── main.py                             # FastAPI backend (recommendation API)
├── app.py                              # Streamlit frontend
├── requirements.txt                    # Python dependencies
├── movies_metadata.csv                 # Raw dataset
├── tfidf_matrix.pkl                    # Saved TF-IDF matrix
├── tfidf.pkl                           # Saved fitted TF-IDF vectorizer
├── indices.pkl                         # Title → index lookup
├── df.pkl                              # Cleaned DataFrame
└── .gitignore
```

---

## 🚀 Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/sibamsamanta7/movie-recommendation-system.git
cd movie-recommendation-system
```

### 2. Create and activate a virtual environment
```bash
python -m venv .venv
.venv\Scripts\Activate.ps1      # Windows PowerShell
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Add the dataset
Download `movies_metadata.csv` (The Movies Dataset) and place it in the project root, then run the notebook once to generate the `.pkl` model artifacts.

### 5. Run the backend (FastAPI)
```bash
uvicorn main:app --reload
```

### 6. Run the frontend (Streamlit)
```bash
streamlit run app.py
```

---

## 📖 How It Works

1. **Data Cleaning** — remove duplicates, handle missing values, parse genres from stringified lists
2. **Feature Engineering** — combine `overview`, `genres`, and `tagline` into a single `tags` feature
3. **Text Preprocessing** — lowercase, remove punctuation, strip stopwords, lemmatize
4. **Vectorization** — convert cleaned text into TF-IDF vectors
5. **Similarity Scoring** — compute cosine similarity between all movie vectors
6. **Recommendation** — for a given title, return the top-N most similar movies

---

## 🔮 Future Improvements

- Add cast, crew, and keyword data for richer recommendations
- Combine with collaborative filtering for a hybrid recommender
- Replace TF-IDF with semantic embeddings (Word2Vec / Sentence-BERT)
- Add evaluation metrics (e.g. precision@k) once user feedback data is available

---

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

## 🙋 Author

**Sibam Samanta**
B.Tech CSE, Meghnad Saha Institute of Technology, Kolkata
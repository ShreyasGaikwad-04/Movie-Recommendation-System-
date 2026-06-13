# 🎬 Movie Recommendation Systems

This repository demonstrates different approaches to building **Movie Recommender Systems** using the [MovieLens Latest Small Dataset](https://grouplens.org/datasets/movielens/latest/).  
Recommender systems are a core application of machine learning in industry — powering platforms like Netflix, Amazon, and Spotify.  

The goal of this project is to **implement, compare, and understand** various recommender techniques:
- Popularity-Based
- Collaborative Filtering (User–User, Item–Item, and Model-Based with Gradient Descent)
- Content-Based (TF-IDF Vectorizer + CSR Matrix)

Special thanks to **GroupLens** for providing the MovieLens dataset 🙌.  

---

## 📊 Dataset Information

We use the **MovieLens Latest Small Dataset** (100k).  

- **Ratings:** 100,836  
- **Users:** 610  
- **Movies:** 9,742  
- **Time Period:** January 09, 1995 – September 26, 2018  

### Files Included
- `ratings.csv` → (userId, movieId, rating, timestamp)  
- `movies.csv` → (movieId, title, genres)  
- `tags.csv` → (userId, movieId, tag, timestamp)  
- `links.csv` → (movieId, imdbId, tmdbId)  

📥 Download here → [MovieLens Dataset Page](https://grouplens.org/datasets/movielens/latest/)  

---

## 🧠 Approaches Implemented

### 1️⃣ Popularity-Based Recommender
- Very simple baseline approach.  
- Recommends the most popular or highest-rated movies.  
- **Pros:** Easy to implement, works for new users.  
- **Cons:** Same recommendations for everyone (no personalization).  

---

### 2️⃣ Collaborative Filtering

Recommends movies based on **user-item interaction patterns**.  

- **User–User Filtering**  
  Finds users similar to the target user and recommends movies liked by those similar users.  

- **Item–Item Filtering**  
  Recommends movies similar to the ones a user has already liked.  

- **Model-Based Collaborative Filtering (Matrix Factorization)**  
  Implemented **from scratch using Gradient Descent** instead of relying on libraries.  
  - Factorizes the user–item rating matrix into **latent user features** and **latent movie features**.  
  - Uses **gradient descent optimization** to minimize the prediction error (MSE).  
  - Learns hidden patterns like user taste (action/sci-fi/romance preference) and item properties.  

This custom implementation shows the inner working of recommendation models rather than treating them as black boxes.  

---

### 3️⃣ Content-Based Filtering

Recommends movies similar in **content (metadata)** to movies the user already likes.  

- Used **TF-IDF Vectorizer** on movie **genres** and **tags**.  
- Represented movie features as a **sparse matrix in CSR format** for memory efficiency.  
- Computed **cosine similarity** between movies directly from the CSR matrix.  

This allows fast and scalable similarity searches even for thousands of movies.  

---

## 📁 Files in Repository
- **`popularity_based.ipynb`** → Implements a simple popularity-based movie recommender.  
- **`collaborative_filtering.ipynb`** → Implements all three collaborative approaches:  
  - User–User similarity  
  - Item–Item similarity  
  - Model-Based Matrix Factorization (from scratch using Gradient Descent).  
- **`content_based.ipynb`** → Uses TF-IDF + CSR sparse matrix for fast similarity-based recommendations.  
- **`README.md`** → Project documentation, approach explanation, dataset info.

---# Movie-Recommendation-System-

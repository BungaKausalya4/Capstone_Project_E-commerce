# Capstone_Project_E-commerce

Judul Project: Analisis Sentimen Ulasan Pelanggan untuk Optimalisasi Strategi E-commerce

1. Project Overview
   Ulasan pelanggan sangat berpengaruh terhadap kepercayaan dan keputusan pembelian. Namun, jumlah ulasan yang besar membuat e-commerce kesulitan memilah secara manual. Proyek ini bertujuan untuk menganalisis sentimen ulasan pelanggan (positif, netral, negatif) menggunakan teknik NLP + Machine Learning, sehingga dapat mendukung strategi bisnis berbasis data.

Dataset: Amazon Product Review Dataset (Kaggle)

2. Raw Dataset
   Amazon Fine Food Reviews Dataset (Kaggle)
   [https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews](https://www.kaggle.com/datasets/arhamrumi/amazon-product-reviews?resource=download)
   File: Reviews.csv
   Total data: ≈ 568.454 ulasan
   Kolom digunakan: Text, Summary, Score, HelpfulnessNumerator

3. Insight & Findings
   🔹 Modeling & Evaluasi
      Baseline Models:
      Logistic Regression → Accuracy 0.75
      Random Forest → Accuracy 0.83
      XGBoost (Default) → Accuracy 0.83
      XGBoost (Tuned) → Accuracy 0.85 ✅ terbaik
   
      Temuan:
      Sentimen positif mudah dikenali.
      Sentimen netral sering tertukar dengan kelas lain.
      XGBoost tuned lebih unggul dibanding default.

  🔹 Feature Importance
      Rating bintang → indikator utama sentimen.
      Teks ulasan → kata emosional (“great”, “disappointed”) sangat berpengaruh.
      Helpfulness votes → semakin banyak, semakin valid.
      Summary → sinyal tambahan untuk sentimen.

  🔹 Visualisasi
      Confusion Matrix → menunjukkan kelemahan pada kelas netral.
      WordCloud:
      Positif → great, love, delicious
      Negatif → bad, disappointed, terrible

  🔹 Contoh Prediksi
      Review: “Great taffy at a great price. There was a wide assortment…”
      Label asli: Positive
      Prediksi model: Positive (probabilitas tinggi)
      Insight: Model menangkap kata-kata positif (great, price, assortment).

4. AI Support Explanation
   Selain modeling klasik, proyek ini menggunakan IBM Granite (LLM) via LangChain + Replicate untuk:
   - Merangkum & mengklasifikasikan sampel ulasan.
   - Menggali insight (positif & negatif dominan).
   - Menghasilkan rekomendasi actionable untuk strategi bisnis.

  🔹 Granite Insights (contoh):
      - K-Cup Coffee → Positive (puas variasi rasa)
      - Dried Mango → Positive (harga kompetitif, sehat)
      - Pretzels → Neutral (hanya hadiah, tidak bisa nilai kualitas)

  🔹 Rekomendasi Actionable
      - Perluas variasi produk populer (contoh: K-Cup).
      - Jaga harga kompetitif (contoh: dried mango).
      - Sorot produk ramah alergi (contoh: dog treats).

Tools: Python (pandas, numpy, scikit-learn, xgboost, matplotlib, seaborn, wordcloud), LangChain, Replicate (IBM Granite).

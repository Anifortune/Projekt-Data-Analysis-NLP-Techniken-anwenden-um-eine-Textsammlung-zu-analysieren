# NLP-Projekt zur Themen- und Sentimentanalyse von Produktrezensionen

import pandas as pd
import numpy as np
import re
import nltk
import gensim
import matplotlib.pyplot as plt
import seaborn as sns
import os

from nltk.corpus import stopwords
from nltk.tokenize import word_tokenize
from nltk.stem import WordNetLemmatizer
from sklearn.feature_extraction.text import CountVectorizer, TfidfVectorizer
from sklearn.decomposition import LatentDirichletAllocation, NMF
from gensim.models import CoherenceModel
from gensim.corpora import Dictionary

# Falls notwendig, NLTK-Resourcen herunterladen
nltk.download('stopwords')
nltk.download('punkt')
nltk.download('wordnet')

### 1️⃣ DATENLADEN ###
df = pd.read_csv("/Users/sarahmannes/Downloads/NLP Analyse/311_Service_Requests.csv", usecols=["Complaint Type", "Descriptor", "Location Type", "Incident Zip", "City", "Borough", "Resolution Description"])
df = df.dropna(subset=["Complaint Type", "Resolution Description"])  # Entferne fehlende Werte

### 2️⃣ TEXTVORBEREITUNG ###
lemmatizer = WordNetLemmatizer()
stop_words = set(stopwords.words('english'))

def preprocess_text(text):
    text = text.lower()
    text = re.sub(r'\d+', '', text)
    text = re.sub(r'[^\w\s]', '', text)
    tokens = word_tokenize(text)
    tokens = [lemmatizer.lemmatize(word) for word in tokens if word not in stop_words]
    return " ".join(tokens)

df["clean_text"] = df["Resolution Description"].astype(str).apply(preprocess_text)

df["clean_text"].to_csv("bereinigte_beschwerden.txt", index=False, header=False)
print("✅ Datei 'bereinigte_beschwerden.txt' wurde erfolgreich gespeichert!")

### 3️⃣ TEXTE IN NUMERISCHE VEKTOREN UMWANDELN ###
vectorizer_bow = CountVectorizer(max_features=1000)
bow_matrix = vectorizer_bow.fit_transform(df["clean_text"])

vectorizer_tfidf = TfidfVectorizer(max_features=1000)
tfidf_matrix = vectorizer_tfidf.fit_transform(df["clean_text"])

print("BoW Shape:", bow_matrix.shape)
print("TF-IDF Shape:", tfidf_matrix.shape)

with open("vektorisierung.txt", "w", encoding="utf-8") as file:
    file.write(f"BoW Shape: {bow_matrix.shape}\n")
    file.write(f"TF-IDF Shape: {tfidf_matrix.shape}\n")
print("✅ Datei 'vektorisierung.txt' wurde erfolgreich gespeichert!")

### 4️⃣ THEMENEXTRAKTION (LDA & NMF) ###
def save_topics_to_file(model, feature_names, filename, n_words=10):
    with open(filename, "w", encoding="utf-8") as file:
        for topic_idx, topic in enumerate(model.components_):
            topic_words = " | ".join([feature_names[i] for i in topic.argsort()[:-n_words - 1:-1]])
            file.write(f"🔹 Thema {topic_idx+1}: {topic_words}\n")
    print(f"✅ Datei '{filename}' wurde erfolgreich gespeichert!")

lda_model = LatentDirichletAllocation(n_components=5, random_state=42)
lda_model.fit(bow_matrix)
print("\n📌 LDA Themen:")
save_topics_to_file(lda_model, vectorizer_bow.get_feature_names_out(), "lda_themen.txt")

nmf_model = NMF(n_components=5, random_state=42)
nmf_model.fit(tfidf_matrix)
print("\n📌 NMF Themen:")
save_topics_to_file(nmf_model, vectorizer_tfidf.get_feature_names_out(), "nmf_themen.txt")

### 5️⃣ COHERENCE SCORE BERECHNEN ###
texts = [text.split() for text in df["clean_text"]]
dictionary = Dictionary(texts)
corpus = [dictionary.doc2bow(text) for text in texts]
lda_gensim = gensim.models.LdaModel(corpus=corpus, id2word=dictionary, num_topics=5, passes=10)
coherence_model_lda = CoherenceModel(model=lda_gensim, texts=texts, dictionary=dictionary, coherence='c_v')

coherence_score = f"🔎 Coherence Score für LDA: {coherence_model_lda.get_coherence():.4f}\n"
print(coherence_score)

with open("coherence_score.txt", "w", encoding="utf-8") as file:
    file.write(coherence_score)
print("✅ Datei 'coherence_score.txt' wurde erfolgreich gespeichert!")

### 6️⃣ VISUALISIERUNG DER THEMEN ###
plt.figure(figsize=(10, 5))
sns.barplot(x=[f'Thema {i+1}' for i in range(5)], y=lda_model.components_.sum(axis=1))
plt.title("Anzahl der Wörter pro Thema (LDA)")
plt.xlabel("Thema")
plt.ylabel("Wort-Häufigkeit")
plt.savefig("lda_visualisierung.png")
plt.show()
print("✅ Datei 'lda_visualisierung.png' wurde erfolgreich gespeichert!")


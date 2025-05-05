# 📦 NLP-Projekt zur Themen- und Sentimentanalyse von Produktrezensionen

Dieses Projekt analysiert unstrukturierte Produktbewertungen (aus dem Lebensmittel- und Haustierbereich) mithilfe moderner NLP-Methoden. Ziel ist es, häufige Themen automatisch zu extrahieren, die Qualität der Themenmodellierung zu bewerten und die Stimmung der Rezensionen zu klassifizieren.  

---

## 📌 Zielsetzung

Das Projekt dient der automatischen Erkennung relevanter Themen und Stimmungen in großen Mengen unstrukturierter Textdaten (Amazon-Produktrezensionen). Es verbindet mehrere semantische Analysetechniken, um Muster und Erkenntnisse herauszufiltern, die für Unternehmen, Forschung oder Marktforschung nützlich sein können.

---

## 🔍 Analyse-Workflow

### 1️⃣ **Datenquelle**
- **Datei**: [`Reviews.csv`](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
- **Inhalt**: Kundenrezensionen (Text, Bewertung, Metadaten)
- **Importpfad**: `/Users/sarahmannes/Downloads/NLP Analyse/Reviews.csv`

---

### 2️⃣ **Vorverarbeitung**
- Entfernen von Zahlen, Sonderzeichen, HTML-Tags (`<br>`), irrelevanten Begriffen
- Tokenisierung & Lemmatisierung
- Speicherung als `bereinigte_reviews.txt`

---

### 3️⃣ **Vektorisierung**
- Bag-of-Words (BoW)
- TF-IDF
- Ergebnisgrößen in `vektorisierung.txt`

---

### 4️⃣ **Themenmodellierung**
- Latent Dirichlet Allocation (LDA) auf BoW
- Non-negative Matrix Factorization (NMF) auf TF-IDF
- Automatische Themenbenennung via Fuzzy Matching mit Schlagwortlisten
- Ergebnisse:
    - `lda_themen.txt`
    - `nmf_themen.txt`

---

### 5️⃣ **Coherence Scores**
- Berechnung mit `gensim`
- Für beide Modelle:
    - LDA: `coherence_score.txt`
    - NMF: wird ebenfalls hinzugefügt

---

### 6️⃣ **Sentimentanalyse**
- VADER SentimentIntensityAnalyzer
- Score zwischen -1 (negativ) und +1 (positiv)
- Speicherung als `sentiment_analyse.txt`

---

### 7️⃣ **Visualisierungen**
- LDA-Themenverteilung (`lda_visualisierung.png`)
- Sentimentverteilung (`sentiment_verteilung.png`)
- Wordclouds pro Thema (`wordcloud_lda_X.png`, `wordcloud_nmf_X.png`)
- Gesamtübersicht der wichtigsten Ergebnisse (`ergebnisse_uebersicht.txt`)

---

## 📂 Erzeugte Dateien

| Datei                            | Beschreibung                                          |
|----------------------------------|-------------------------------------------------------|
| `bereinigte_reviews.txt`         | Vorverarbeitete Rezensionstexte                       |
| `vektorisierung.txt`             | Matrixgrößen von BoW und TF-IDF                       |
| `lda_themen.txt`                 | Extrahierte Themen mit LDA inkl. Benennung            |
| `nmf_themen.txt`                 | Extrahierte Themen mit NMF inkl. Benennung            |
| `coherence_score.txt`            | Coherence Scores für LDA und NMF                      |
| `sentiment_analyse.txt`          | Sentiment-Score pro Text                              |
| `lda_visualisierung.png`         | Visualisierung der Wortverteilung pro LDA-Thema       |
| `sentiment_verteilung.png`       | Histogramm der Sentimentverteilung                   |
| `wordcloud_lda_X.png`            | Wordclouds pro LDA-Thema                             |
| `wordcloud_nmf_X.png`            | Wordclouds pro NMF-Thema                             |
| `ergebnisse_uebersicht.txt`      | Zusammenfassung der wichtigsten Analyseergebnisse     |

---

## 🛠️ Verwendete Technologien

- **Python 3.12+**
- **Pandas, NumPy**
- **NLTK**
- **Scikit-learn**
- **Gensim**
- **Matplotlib, Seaborn**
- **WordCloud**
- **RapidFuzz**

---

## 🔧 Technische Beschreibung & Nutzung

Die detaillierte technische Beschreibung, alle Installationshinweise und Anwendungsanleitungen findest du in dieser README.  
Die finale Dokumentation (Abstract, Reflexion, Zusammenfassung) ist separat als PDF eingereicht.  
Der vollständige Code liegt im GitHub-Repository:  
➡ **[GitHub-Link hier einfügen]**

### So führst du das Projekt aus:
1. Stelle sicher, dass alle in `requirements.txt` oder der README genannten Bibliotheken installiert sind.
2. Lade die Datei `Reviews.csv` aus [Kaggle](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews) herunter und speichere sie im Ordner:  
   `/Users/sarahmannes/Downloads/NLP Analyse/`
3. Führe das Python-Skript (`.py` oder Jupyter Notebook) aus.
4. Die Ausgabe wird automatisch in die beschriebenen Text-, Bild- und CSV-Dateien geschrieben.

---

## 📈 Ergebnisse & Reflexion

- Ziel: Automatische Themen- und Sentimentanalyse großer Textmengen.
- Ergebnis: Die Modelle identifizieren nachvollziehbare Themen (z. B. Pet Products, Taste & Quality, Packaging) und zeigen klare Stimmungstendenzen.
- Reflexion: Durch die Arbeit konnten verschiedene semantische Analysetechniken erfolgreich kombiniert und evaluiert werden.  
  Herausforderungen wie die Datenbeschaffung (von 311 NYC zu Amazon-Bewertungen) und die Themenbenennung wurden mit pragmatischen Lösungsstrategien (Fuzzy Matching, Schlagwortlisten) gemeistert.
- Ausblick: Künftige Arbeiten könnten Word Embeddings (BERT, Word2Vec) oder aspektbasierte Sentimentanalysen einbeziehen, um tiefere inhaltliche Zusammenhänge zu erschließen.

---

© 2025 – Projekt Data Analysis & NLP-Techniken  
MIT License  



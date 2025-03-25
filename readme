# 🧠 NLP-Projekt zur Themen- und Sentimentanalyse von Produktrezensionen

Dieses Projekt analysiert unstrukturierte Produktbewertungen (aus dem Lebensmittelbereich) mithilfe moderner NLP-Methoden. Ziel ist es, häufige Themen automatisch zu extrahieren, die Qualität der Themenmodellierung zu bewerten und die Stimmung der Rezensionen zu klassifizieren.

---

## 📌 Zielsetzung

Ziel ist es, aus einer großen Menge unstrukturierter Texte (Produktrezensionen von Amazon) **automatisch Themen** zu identifizieren und **Stimmungen zu analysieren**, um daraus **relevante Erkenntnisse** für Unternehmen oder Entscheidungsträger zu gewinnen.

---

## 🔍 Analyse-Workflow

### 1️⃣ **Datenquelle**
- **Datei**: [`Reviews.csv`](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
- **Inhalt**: Kundenrezensionen inkl. Text, Bewertung, Produktinformationen
- **Importpfad**: `/Users/sarahmannes/Downloads/NLP Analyse/Reviews.csv`

### 2️⃣ **Vorverarbeitung**
- Entfernen von Sonderzeichen, Zahlen, HTML-Tags (`<br>`), häufige Stoppwörter und irrelevante Begriffe
- Tokenisierung & Lemmatisierung
- Speicherung als `bereinigte_beschwerden.txt`

### 3️⃣ **Vektorisierung**
- Bag-of-Words (BoW)
- TF-IDF
- Ausgabe der Dimensionen in `vektorisierung.txt`

### 4️⃣ **Themenmodellierung**
- **LDA** (Latent Dirichlet Allocation) auf BoW
- **NMF** (Non-negative Matrix Factorization) auf TF-IDF
- Automatische **Themenbenennung** per Fuzzy Matching
- Speicherung in `lda_themen.txt` & `nmf_themen.txt`

### 5️⃣ **Coherence Score**
- Berechnung mit `gensim`
- Ausgabe in `coherence_score.txt` zur Bewertung der Modellqualität

### 6️⃣ **Sentimentanalyse**
- VADER SentimentIntensityAnalyzer
- Score zwischen -1 (negativ) und +1 (positiv)
- Ergebnisse in `sentiment_analyse.txt`

### 7️⃣ **Visualisierung**
- **Themenverteilung (LDA)**: `lda_visualisierung.png`
- **Sentimentverteilung**: `sentiment_verteilung.png`

---

## 📂 Erzeugte Dateien

| Datei                         | Beschreibung                                         |
|------------------------------|------------------------------------------------------|
| `bereinigte_beschwerden.txt` | Vorverarbeitete Rezensionstexte                      |
| `vektorisierung.txt`         | Matrixgrößen von BoW und TF-IDF                      |
| `lda_themen.txt`             | Extrahierte Themen mit LDA + automatische Benennung  |
| `nmf_themen.txt`             | Extrahierte Themen mit NMF + automatische Benennung  |
| `coherence_score.txt`        | Coherence Score zur Modellvalidierung                |
| `sentiment_analyse.txt`      | Sentiment-Score für jeden Text                       |
| `lda_visualisierung.png`     | Visualisierung der Wortverteilung pro LDA-Thema      |
| `sentiment_verteilung.png`   | Histogramm der Sentimentverteilung                   |

---

## 🛠️ Verwendete Technologien

- **Python** (3.12+)
- **Pandas, NumPy**
- **NLTK**
- **Scikit-Learn**
- **Gensim**
- **Matplotlib & Seaborn**
- **WordCloud**
- **RapidFuzz** (für fuzzy topic matching)

---

## 🧪 Beispiel für extrahierte Themen

```text
🔹 Thema 1 (Pet Products): food | dog | treat | cat | love | eat | day | snack | chewy | animal
🔹 Thema 2 (Taste & Quality): taste | like | flavor | chocolate | sweet | sugar | good | great | snack | product
🔹 Thema 3 (Packaging & Delivery): package | bag | box | time | order | delivery | arrived | seal | shipping | bottle
🔹 Thema 4 (Price & Value): price | cost | worth | cheap | affordable | deal | value | buy | expensive | low
🔹 Thema 5 (Nutrition & Ingredients): sugar | protein | fat | calorie | healthy | ingredient | salt | organic | natural | gluten

# 📊 NLP-Analyse von Produktbewertungen mit LDA & NMF

Dieses Projekt analysiert **Produktbewertungen** mittels **Natural Language Processing (NLP)**, um häufig diskutierte Themen zu extrahieren.  
Dazu werden **Latent Dirichlet Allocation (LDA)** und **Non-Negative Matrix Factorization (NMF)** verwendet.

🚀 **Ziel des Projekts:**  
- Extraktion häufig diskutierter Themen aus Kundenbewertungen
- Analyse der **Stimmung (Sentiment)** der Rezensionen
- Identifikation von Verbesserungspotenzialen für Produkte
- Optimierung des NLP-Workflows für große Datensätze

---

## 📂 **Datenquelle**
Die verwendeten Daten stammen aus:
- **Amazon Fine Food Reviews Dataset**  
  - Link: [Kaggle Dataset](https://www.kaggle.com/datasets/snap/amazon-fine-food-reviews)
  - Enthält ca. **500.000 Kundenrezensionen** mit Bewertungen von 1 bis 5 Sternen.

---

## 🔧 **Technischer Workflow**

1️⃣ **Datenladen & Bereinigung**
   - Entfernen von **Stoppwörtern & Sonderzeichen**
   - Lemmatisierung der Wörter

2️⃣ **Text-Vektorisierung**
   - **Bag-of-Words (BoW)**: Wortzählung
   - **TF-IDF (Term Frequency - Inverse Document Frequency)**

3️⃣ **Themenextraktion mit LDA & NMF**
   - Identifikation der **5 wichtigsten Themen**
   - Automatische **Themenbenennung** anhand vordefinierter Kategorien

4️⃣ **Berechnung des Coherence Scores**
   - Validierung der **Themenqualität** durch einen **Coherence Score**  
   - **Höherer Wert** = **bessere Themenkonsistenz**

5️⃣ **Sentiment-Analyse**
   - Bewertung, ob Rezensionen **positiv, neutral oder negativ** sind.

6️⃣ **Erstellung von Visualisierungen**
   - **Themenverteilung (LDA)**
   - **Histogramm der Sentiment-Scores**

---

## 🛠 **Installation & Nutzung**

### 1️⃣ **Vorbereitungen**
Stelle sicher, dass du **Python 3.8+** installiert hast.  

### 2️⃣ **Benötigte Bibliotheken installieren**
Falls nicht vorhanden, installiert das Skript automatisch alle notwendigen Pakete.  
Falls du das manuell tun möchtest, führe folgenden Befehl aus:

```bash
pip install pandas numpy nltk gensim matplotlib seaborn wordcloud rapidfuzz scikit-learn
3️⃣ Skript ausführen
Kopiere die Datei Reviews.csv in den Ordner "NLP Analyse" in deinem Download-Verzeichnis.
Dann starte das Skript mit:

bash
Kopieren
Bearbeiten
python nlp_analysis.py
Nach Abschluss findest du folgende Ergebnisse als Dateien:

bereinigte_reviews.txt → Vorbereitete Texte
vektorisierung.txt → Shape der Vektormatrizen
lda_themen.txt → Identifizierte LDA-Themen
nmf_themen.txt → Identifizierte NMF-Themen
coherence_score.txt → Qualitätsbewertung der Themen
lda_visualisierung.png → Diagramm zur Themenverteilung
sentiment_analyse.txt → Bewertung der Sentiments
sentiment_verteilung.png → Verteilung positiver/negativer Rezensionen
📊 Beispielausgabe
🔹 Extrahierte Themen (LDA)
pgsql
Kopieren
Bearbeiten
🔹 Thema 1 (Product Quality): durable | well-made | reliable | sturdy | broken | defective
🔹 Thema 2 (Customer Service): support | warranty | helpful | refund | return | replacement
🔹 Thema 3 (Shipping & Packaging): delivery | shipping | box | arrived | damaged | fast
🔹 Thema 4 (Price & Value): cheap | expensive | worth | value | overpriced | discount
🔹 Thema 5 (User Experience): easy | setup | instructions | user-friendly | comfortable
📊 Themenvisualisierung (LDA)


📈 Sentiment-Analyse
makefile
Kopieren
Bearbeiten
Positiv: 78%
Neutral: 12%
Negativ: 10%


📝 Lizenz
Dieses Projekt steht unter der MIT-Lizenz, d.h. du kannst den Code frei nutzen, verändern und weiterverbreiten.


🚀 Erstellt von: Sarah Mannes
📅 Letzte Aktualisierung: März 2025

yaml
Kopieren
Bearbeiten

---





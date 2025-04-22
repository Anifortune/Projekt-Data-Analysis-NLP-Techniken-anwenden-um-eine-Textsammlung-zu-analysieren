# NLP-Projekt zur Themen- und Sentimentanalyse von Produktrezensionen

# 📦 Projekt: Themenmodellierung und Sentimentanalyse auf Produktbewertungen

Dieses Projekt untersucht mithilfe moderner NLP-Methoden die Themen und Stimmungen, die in Amazon-Produktbewertungen aus den Bereichen Lebensmittel und Haustierbedarf enthalten sind. Die Analyse basiert auf dem öffentlich verfügbaren Datensatz "Reviews.csv" und wurde im Rahmen einer Studienleistung durchgeführt.

---

## 📋 Aufgabenstellung und Zielsetzung

Die Aufgabe bestand darin, unstrukturierte Textdaten zu analysieren und:
- semantische Themen zu extrahieren,
- zwei verschiedene semantische Analysetechniken (LDA und NMF) zu vergleichen,
- eine Sentimentanalyse durchzuführen,
- eine Coherence Score-Bewertung der Themenmodelle durchzuführen,
- die Ergebnisse nachvollziehbar zu dokumentieren.

Ursprünglich war die Analyse des NYC-311-Beschwerdedatensatzes vorgesehen. Aufgrund technischer Exportprobleme und unzureichender Datenqualität wurde jedoch ein alternativer Datensatz mit über 500.000 englischsprachigen Produktbewertungen (Reviews.csv) verwendet.

---

## 🔧 Technische Beschreibung und Nutzung des Codes

### Voraussetzungen
- Python 3.12 oder höher
- Empfohlen: Nutzung in einer JupyterLab-Umgebung (z. B. Anaconda)
- Der Datensatz "Reviews.csv" liegt im lokalen Verzeichnis: `/Users/sarahmannes/Downloads/NLP Analyse/Reviews.csv`

### Installation benötigter Bibliotheken
Die notwendigen Bibliotheken werden beim ersten Start automatisch installiert (sofern nicht vorhanden). Dazu gehören u. a. `nltk`, `gensim`, `scikit-learn`, `matplotlib`, `seaborn`, `pandas`, `wordcloud`, `rapidfuzz`.

### Ausführung
1. Stelle sicher, dass sich die Datei `Reviews.csv` im Pfad befindet: `/Users/sarahmannes/Downloads/NLP Analyse/`
2. Führe den Code in Jupyter Lab oder einer Python-IDE deiner Wahl aus.
3. Die Ergebnisse werden automatisch in die folgenden Dateien geschrieben:
   - `bereinigte_reviews.txt`
   - `vektorisierung.txt`
   - `lda_themen.txt`
   - `nmf_themen.txt`
   - `coherence_score.txt`
   - `lda_visualisierung.png`
   - `sentiment_analyse.txt`
   - `sentiment_verteilung.png`

Hinweis: Die technische Dokumentation sowie die Beschreibung zur Nutzung des Codes befinden sich auch direkt im GitHub-Repository (README-Datei).

---

## 🔍 Verwendete Methoden

### Textvorverarbeitung
- Entfernung von Sonderzeichen, HTML-Tags, Zahlen, irrelevanten Wörtern
- Tokenisierung, Lemmatisierung
- Speicherung in `bereinigte_reviews.txt`

### Vektorisierung
- `BoW` (Bag of Words)
- `TF-IDF` (Term Frequency-Inverse Document Frequency)
- Vergleich der Repräsentationen in `vektorisierung.txt`

### Themenextraktion
- `Latent Dirichlet Allocation (LDA)`
- `Non-negative Matrix Factorization (NMF)`
- Themenbenennung über Fuzzy Matching gegen vordefinierte Keyword-Cluster
- Ausgabe: `lda_themen.txt`, `nmf_themen.txt`

### Coherence Score Bewertung
- Für LDA und NMF mittels `CoherenceModel` aus `gensim`
- Ausgabe in `coherence_score.txt`

### Visualisierung
- LDA-Themenverteilung: `lda_visualisierung.png`
- Sentiment-Verteilung: `sentiment_verteilung.png`

### Sentimentanalyse
- Durchführung mit VADER (NLTK)
- Ergebnisse in `sentiment_analyse.txt`

---

## 📁 Ergebnisdateien (automatisch generiert)

| Datei | Beschreibung |
|-------|--------------|
| `bereinigte_reviews.txt` | Vorverarbeitete Texte |
| `vektorisierung.txt` | BoW- und TF-IDF-Matrixdimensionen |
| `lda_themen.txt` | Top-10-Wörter pro LDA-Thema mit Benennung |
| `nmf_themen.txt` | Top-10-Wörter pro NMF-Thema mit Benennung |
| `coherence_score.txt` | Coherence Scores für LDA und NMF |
| `lda_visualisierung.png` | Balkendiagramm der LDA-Themenhäufigkeit |
| `sentiment_analyse.txt` | Sentiment-Scores pro Bewertung |
| `sentiment_verteilung.png` | Histogramm der Sentiment-Verteilung |

---

## 🔗 GitHub-Repository

Das gesamte Projekt ist öffentlich zugänglich unter:
[https://github.com/Anifortune/Projekt-Data-Analysis-NLP-Techniken-anwenden-um-eine-Textsammlung-zu-analysieren](https://github.com/Anifortune/Projekt-Data-Analysis-NLP-Techniken-anwenden-um-eine-Textsammlung-zu-analysieren)

---

## 🧠 Autorin & Lizenz
Sarah Mannes  
MIT License © 2025


### 📜 **README.md**  

```md
# 🏙 NLP-Analyse von Beschwerden aus New York City 311 Service Requests  

## 📌 Projektbeschreibung  
Dieses Projekt nutzt **Natural Language Processing (NLP)**, um häufig diskutierte Themen aus **NYC 311 Service Requests** zu extrahieren.  
Ziel ist es, **Entscheidungsträgern** eine datengestützte Analyse bereitzustellen, um Probleme in der Stadtverwaltung besser zu verstehen.  

🔍 **Analyse-Schritte:**  
1️⃣ **Datenabruf**: Laden und Vorverarbeitung von **Beschwerdedaten** aus dem öffentlichen NYC 311-Datensatz.  
2️⃣ **Datenbereinigung**: Tokenisierung, Lemmatisierung, Entfernen von Stoppwörtern und irrelevanten Zeichen.  
3️⃣ **Themenmodellierung**: Analyse mit **LDA** (Latent Dirichlet Allocation) und **NMF** (Non-Negative Matrix Factorization).  
4️⃣ **Vektorisierung**: Umwandlung der Texte mit **BoW (Bag-of-Words)** und **TF-IDF**.  
5️⃣ **Sentiment-Analyse**: Bewertung der Beschwerdetexte mit VADER Sentiment Analysis.  
6️⃣ **Erstellung von Visualisierungen** für **Themen-Häufigkeit** und **Sentiment-Verteilung**.  
7️⃣ **Berechnung des Coherence Scores**, um die Qualität der Themenmodelle zu bewerten.  

---

## 📊 **Datenquelle**  
📂 **NYC 311 Service Requests**  
🔗 **Daten abrufen auf Kaggle:** [Hier ansehen](https://www.kaggle.com/datasets/pablomonleon/311-service-requests-nyc))  

🔹 **Relevante Spalten für die Analyse:**  
- **Complaint Type** (Art der Beschwerde)  
- **Descriptor** (Detailbeschreibung)  
- **Location Type** (Ort der Beschwerde)  
- **Incident Zip** (Postleitzahl)  
- **City** (Stadtbezirk)  
- **Borough** (Stadtteil)  
- **Resolution Description** (Behördliche Antwort auf die Beschwerde)  

---

## ⚙ **Installation & Nutzung in Jupyter Lab**  
### 🛠 **Voraussetzungen:**  
1️⃣ **Python 3.8+**  
2️⃣ **Jupyter Lab oder Jupyter Notebook**  
3️⃣ **Notwendige Python-Bibliotheken (NLTK, Gensim, Scikit-Learn, etc.)**  

### ▶ **Bibliotheken in Jupyter installieren:**  
Falls einige Bibliotheken fehlen, können sie direkt in Jupyter installiert werden:  
```python
!pip install pandas numpy nltk gensim matplotlib seaborn wordcloud scikit-learn
```

### ▶ **Notebook ausführen:**  
1️⃣ **Starte Jupyter Lab**  
2️⃣ **Öffne das Notebook und führe alle Zellen nacheinander aus.**  
3️⃣ **Die Ergebnisse werden automatisch gespeichert und visualisiert.**  

---

## 📂 **Erstellte Dateien & Ergebnisse**  
Nach der Ausführung werden folgende Dateien generiert:  

| Datei                     | Beschreibung |
|---------------------------|-------------|
| `bereinigte_beschwerden.txt` | Enthält die vorverarbeiteten Beschwerdetexte. |
| `vektorisierung.txt` | Informationen über die **BoW & TF-IDF Vektorisierung** (Matrix-Shape). |
| `lda_themen.txt` | Enthält die extrahierten Themen mit **LDA**. |
| `nmf_themen.txt` | Enthält die extrahierten Themen mit **NMF**. |
| `coherence_score.txt` | Berechnung des **Coherence Scores** zur Themenvalidierung. |
| `sentiment_analyse.txt` | Ergebnisse der **Sentiment-Analyse** mit Sentiment-Werten. |
| `lda_visualisierung.png` | **Balkendiagramm** mit den wichtigsten Wörtern pro Thema (LDA). |
| `sentiment_verteilung.png` | **Histogramm** der Sentiment-Verteilung der Beschwerden. |

---

## 🔬 **Methoden & Technologien**  
🛠 **Technologien:**  
✅ **Python** (pandas, NumPy, matplotlib, seaborn)  
✅ **NLP-Techniken** (NLTK, Gensim, Scikit-Learn)  
✅ **Themenmodellierung** (LDA, NMF)  
✅ **Sentiment-Analyse** (VADER)  
✅ **Vektorisierung** (BoW, TF-IDF)  
✅ **Coherence Score** zur Evaluierung  

📌 **Wichtige Erklärungen:**  
- **LDA (Latent Dirichlet Allocation):** Probabilistisches Modell zur automatischen Themenentdeckung.  
- **NMF (Non-Negative Matrix Factorization):** Deterministisches Modell zur Themenidentifikation.  
- **TF-IDF (Term Frequency - Inverse Document Frequency):** Gewichtet Wörter nach Relevanz in Dokumenten.  

---

## 📜 **Lizenz**  
Dieses Projekt steht unter der **MIT-Lizenz**, die es erlaubt, den Code frei zu nutzen, zu modifizieren und zu verbreiten.  

📜 **MIT License** – [Mehr Informationen](https://opensource.org/licenses/MIT)  

---

## 🚀 **Status & To-Do**  
✅ **Datenaufbereitung & Bereinigung**  
✅ **Themenmodellierung mit LDA & NMF**  
✅ **Vektorisierung mit BoW & TF-IDF**  
✅ **Sentiment-Analyse & Coherence Score**  
✅ **Visualisierungen & Ergebnisexport**  
❌ **Korrekte Themenbenennung der LDA Visualisierung**


📌 **Mögliche Erweiterungen:**  
- 🔍 **Clustering** von Beschwerden basierend auf Themen.  
- 📌 **Deep Learning** für präzisere Textklassifikation.  
- 📊 **Dashboards** zur interaktiven Visualisierung der Daten.  

---

🚀 **Projektstatus: Bereit zur Abgabe Phase 2**  
📩 **Feedback & Erweiterungsideen willkommen!**  
```

---

# AI-Based Hate Speech Detection System

An end-to-end Machine Learning web application designed to automatically classify text content into three distinct categories: **Hate Speech**, **Offensive Language**, or **Neutral**. Built using modern Python micro-frameworks and statistical Natural Language Processing (NLP) methodologies.

---

## System Architecture & ML Pipeline:

The platform ingests text data and processes it through a sequential, modular pipeline before classification:
### 1. Advanced Preprocessing Pipeline:
Utilizes advanced regex templates combined with the **NLTK (Natural Language Toolkit)** suite to eliminate text noise:
* **Token Normalization:** Forces low-case transformation across all token characters.
* **Sanitization Regex:** Drops URLs (`http\S+`), Twitter/X user handles (`@\w+`), and hash metadata (`#\w+`).
* **Noise Mitigation:** Scrubs out special entities, numeric digits, and non-alphabetic punctuation marks.
* **Lexicon Filtering:** Filters out English computational grammatical constraints using configured NLTK Stopwords arrays.
* **Morphological Stemming:** Applies the `PorterStemmer` algorithm to strip suffix variants down to root base structures.

### 2. Feature Vectorization:
Translates textual structures into mathematically computational forms via text vectorization:
* **Vector Model:** `CountVectorizer` converts tokens into highly dense matrix metrics mapping string term counts.

### 3. Machine Learning Models Supported:
The system implements and cross-tests four highly robust underlying algorithmic variations:
**Multinomial Naive Bayes (`MultinomialNB`)** — Excellent benchmark baseline for discrete token counting patterns.
**Support Vector Machine (`LinearSVC`)** — Extremely efficient at fitting large margin splits on high-dimensional text structures.
**Logistic Regression** — Maximizes binary/multiclass probability margins configured with an extended `max_iter=2000` bounds check.
**Random Forest Classifier** — Ensembles an array of 100 decision trees to curb overfitting tendencies.

---

## Technology Stack:

* **Core Runtime:** Python 3.8+
* **Backend Framework:** Flask (incorporating Secure Context Sessions & Dynamic App Routing)
* **Storage Engine:** SQLite3 (Handles concurrent structural storage for users and auditing lookup logs)
* **Data Processing:** Pandas, NumPy
* **Machine Learning & NLP:** Scikit-Learn, NLTK
* **Data Visualization:** Matplotlib (config-locked to an isolated non-interactive thread execution layout via `matplotlib.use("Agg")`)

---

## Core Project Structure:

```text
├── models/                     # Serialized optimization file binaries (.pkl)
│   ├── best_model.pkl          # Automated champion pipeline model snapshot
│   ├── vectorizer.pkl          # Configured tokenization parser vocabulary mapping
│   └── [algorithms]_model.pkl  # Extracted algorithmic individual snapshot iterations
├── static/
│   └── graphs/                 # Visual outputs (Confusion Matrices & Comparison Bars)
├── templates/                  # Frontend HTML view interfaces
├── uploads/                    # Cached workspace directory for dataset ingestion
├── app.py                      # Production app execution endpoint script
├── README.md                   # System description and onboarding manual
└── hate_speech_ai.db          # Initialized Local relational SQLite3 schema storage
```

---

## Step-by-Step Installation & Setup Guide:

### 1. Clone the Code Repository
Pull down the project to your local workstation:
```bash
git clone https://github.com/SKMAHABOOBSUBHANI-810/AI-BASED-HATE-SPEECH-DETECTION-USING-NLTK-AND-MACHINE-LEARNING.git
cd AI-BASED-HATE-SPEECH-DETECTION-USING-NLTK-AND-MACHINE-LEARNING
```

### 2. Setup a Python Virtual Environment (Highly Recommended)
Isolate your package dependencies cleanly:
```bash
# Create the environment
python -o venv venv

# Activate the environment (Windows bash shell)
source venv/Scripts/activate

# Activate the environment (Mac/Linux shell)
source venv/bin/activate
```

### 3. Install Required Packages:
Install the required analytical and web service dependencies:
```bash
pip install flask pandas scikit-learn nltk matplotlib
```

### 4. Fire Up the Server Engine:
Launch the web deployment instance onto your local network:
```bash
python app.py
```
Open your preferred web browser and point it to: `http://127.0.0`

---

## Security & Access Control:

To access the administrative portal on your local machine, open your browser and head over to `http://127.0.0admin`. Use the default development credentials provided below:

* **Admin Username:** `admin`
* **Admin Password:** `admin`

> [!WARNING]  
> **Production Notice:** These credentials are explicitly hardcoded inside the `app.py` script for development purposes. Remember to transition these values to safe environment variables (`.env`) or set up a secure hashed authentication routine before launching the platform publicly on live hosting networks (such as Render).

---

## Role-Based Workflow Guide:

### Admin Panel Workflow:
1. Log into the secure dashboard via the `/admin` route entry portal using the default credentials.
2. **Upload Dataset:** Upload any dataset in standard `.csv` file structures holding dedicated `text` and `label` categorical columns.
3. **Preprocess:** Trigger the automated background NLTK parsing mechanism to scrub out data noise.
4. **Train AI:** Simultaneously train all 4 ML models. The server will dynamically compute validation metrics, output structural **Confusion Matrix graphs**, select the highest performing variant, and save it automatically as `best_model.pkl`.
5. **Moderate & Audit:** Oversee flagged user activity lists. System options allow admins to send formal account warnings for *hate speech* classifications or completely block offending credentials.

### User Dashboard Workflow:
1. Register and sign in through the client interface layout.
2. Enter any text string into the active inference field text box.
3. Click check to view the real-time AI model categorization output (*Hate Speech*, *Offensive*, or *Neutral*).
4. Review your previous system logging


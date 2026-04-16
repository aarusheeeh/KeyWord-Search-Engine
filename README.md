### **Simple Keyword Search Engine**

#### **Project Overview**
This project implements a **Simple Keyword Search Engine** using the **Vector Space Model (VSM)**. It utilizes the **TF-IDF (Term Frequency-Inverse Document Frequency)** algorithm and **Cosine Similarity** to rank and retrieve documents from the **CISI Dataset** (a standard Information Retrieval benchmark).
**Dataset Link-** https://www.kaggle.com/datasets/dmaso01dsta/cisi-a-dataset-for-information-retrieval
#### **Core Features**
* **Automated Data Pipeline:** Direct integration with the Kaggle API for dataset retrieval.
* **Text Normalization:** Implements Case Folding, Tokenization, and Noise Removal.
* **Natural Language Processing:** Uses NLTK for Stopword removal and Lemmatization.
* **Mathematical Ranking:** Employs Cosine Similarity to calculate the relevance of documents to a user query.

#### **Prerequisites**
* Python 3.x
* Kaggle Account (for API Key)
* Required Libraries: `pandas`, `scikit-learn`, `nltk`, `kaggle`

#### **Installation & Execution**
1.  **Kaggle Setup:** * Generate a `kaggle.json` file from your Kaggle Account Settings (API section).
    * Upload this file when prompted by the script.
2.  **Run the Script:**
    * Execute the cells in order. The script will automatically download and parse the **CISI dataset**.
3.  **Search:**
    * Call the `search_with_scores("your keywords here")` function to see ranked results.

#### **Methodology**
The engine follows a standard IR pipeline:
1.  **Preprocessing:** Cleaning raw text to remove punctuation and numbers.
2.  **Indexing:** Transforming text into a numerical TF-IDF matrix.
3.  **Retrieval:** Comparing the user query vector against document vectors.
4.  **Ranking:** Sorting results by their similarity percentage.

---

### **How the Dataset is Downloaded**

For your **Methodology** section (and for your Viva), you must explain the automated download process. Here is how the code handles it:

1.  **Authentication:** The code uses the `kaggle.json` file, which contains your username and private API key, to authenticate your session with Kaggle's servers.
2.  **The API Call:** It executes the command `!kaggle datasets download -d dmaso01dsta/cisi-a-dataset-for-information-retrieval`. This communicates directly with Kaggle to find the specific **CISI dataset** repository.
3.  **Transfer & Unzip:** The dataset is downloaded as a compressed `.zip` file to your environment. The code then uses `!unzip` to extract the raw text files (`CISI.ALL`).
4.  **File Parsing:** Since the dataset isn't in a standard format (like CSV), the code reads the `.ALL` text file line-by-line, looking for the `.I` (Identifier) and `.W` (Words) tags to split the large text file into 1,460 individual documents.




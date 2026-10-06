# 🏨 Airbnb NYC Listings: Exploratory Data Analysis & Cleaning

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Pandas](https://img.shields.io/badge/pandas-2.0+-darkgreen.svg)](https://pandas.pydata.org/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

An end-to-end data cleaning and exploratory data analysis (EDA) pipeline for the **Airbnb Open Data** dataset, focused on New York City listings. The project covers data ingestion, parsing-error handling, missing-value treatment, feature simplification, and visual exploration of key distributions.

---

## Table of Contents

- [Key Objectives](#-key-objectives)
- [Tech Stack](#️-tech-stack)
- [Getting Started](#-getting-started)
- [Data Processing Pipeline](#-data-processing-pipeline)
- [Visualizations](#-visualizations)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)
- [Contact](#-contact)

---

## 📌 Key Objectives

1. **Data Curation & Parsing** – Ingest records that contain syntax errors or structural anomalies without breaking the pipeline.
2. **Quality Assurance** – Detect and handle missing values (`NaN`), redundant columns, and incorrect data types (such as dollar amounts stored as text).
3. **Feature Engineering** – Normalize text fields and align the dataset schema.
4. **Insights & Visualizations** – Highlight the distribution of user reviews and regional patterns.

---

## 🛠️ Tech Stack

| Category  | Tools                                   |
|-----------|-----------------------------------------|
| Language  | Python 3.8+                             |
| Libraries | `pandas`, `numpy`, `matplotlib`, `seaborn` |

---

## 🚀 Getting Started

### Prerequisites

- Python 3.8 or higher
- `pip` package manager
- The Airbnb Open Data CSV file (NYC listings)

### Installation

```bash
# Clone the repository
git clone https://github.com/Kirtisheel1/your-repo.git
cd your-repo

# Install dependencies
pip install pandas numpy matplotlib seaborn
```

### Usage

1. Place the raw dataset CSV in the project folder.
2. Open and run the notebook (or script) from top to bottom.
3. The cleaned dataset is saved as `clean_airbnb.csv`.

---

## 🔄 Data Processing Pipeline

### 1. Raw Ingestion & Initial Assessment
- Load the dataset while skipping corrupted or truncated rows using `on_bad_lines='skip'`.
- Audit the structure with `.info()`, `.describe()`, and `.dtypes`.

### 2. Feature-Level Cleaning
- **Financial standardization**: Remove symbols (`$`, `,`) from monetary columns such as `service fee` and convert them to numeric values.
- **Text harmonization**: Standardize categorical fields, for example converting `host_identity_verified` values to uppercase.

### 3. Missing Value & Outlier Strategy
- Drop uninformative features, such as `license`, which is more than 99% null.
- Remove rows with missing values in critical columns to keep the data consistent.
- Exclude redundant columns such as `reviews per month` and `availability 365` to simplify the dataset.

### 4. Downstream Export
- Reset and align index keys, then save the cleaned dataset to `clean_airbnb.csv`.

---

## 📊 Visualizations

**Review Rate Distribution** – An exploded pie chart showing how users rated listings (`review rate number`).

```python
# Visualize review rate distribution
counts = df['review rate number'].value_counts()
plt.pie(
    counts,
    labels=counts.index,
    autopct='%1.1f%%',
    explode=[0.1, 0, 0, 0, 0],
    shadow=True
)
plt.show()
```

---

## 📁 Project Structure

```
your-repo/
├── data/
│   ├── Airbnb_Open_Data.csv   # Raw dataset
│   └── clean_airbnb.csv       # Cleaned output
├── notebook.ipynb             # EDA and cleaning workflow
└── README.md
```

> Adjust file names to match your repository.

---

## 🤝 Contributing

Contributions are welcome. If you would like to improve the cleaning logic or add predictive modeling pipelines:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add your feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a pull request

---

## 📄 License

Distributed under the MIT License. See `LICENSE` for details.

---

## 📬 Contact

**Kirtisheel Chikhlikar** – [kirtisheelchikhlikar@gmail.com](mailto:kirtisheelchikhlikar@gmail.com)  
GitHub: [Kirtisheel1](https://github.com/Kirtisheel1)

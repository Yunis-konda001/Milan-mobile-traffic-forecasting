# Milan Mobile Traffic Forecasting

## Project Overview

This project analyzes mobile network traffic data from Milan, Italy. I built three forecasting models to predict internet usage for one week. The models are Linear Regression, LSTM, and GRU.

---

## What You Need to Run This Code

### Hardware Requirements

| Item      | Minimum                          |
|-----------|----------------------------------|
| RAM       | 8 GB (16 GB recommended)         |
| Storage   | 10 GB free space                 |
| Processor | Any modern Intel or AMD          |

### Software Requirements

| Software   | Version              |
|------------|----------------------|
| Windows 11 | (or Linux/Mac)       |
| Python     | 3.11 or 3.13         |
| pip        | Latest version       |

---

## Pushing to GitHub (without the large data)

The raw telecom folder is **~5–20 GB** and must **not** be committed. This repo uses `.gitignore` to exclude it automatically.

| Included in Git                                              | Excluded from Git                                      |
|--------------------------------------------------------------|--------------------------------------------------------|
| `formative_1.ipynb`, `README.md`, `requirements.txt`         | `Telecommunications - SMS, Call, Internet - MI/`       |
| `milano-grid/` (small geojson)                               | `.venv/`                                               |
| `processed/` (~2 MB caches — enough to rerun Task 3 quickly) | Raw `.txt` day files                                   |


```bash
git rm -r --cached "Telecommunications - SMS, Call, Internet - MI"
git commit -m "Stop tracking raw telecom data"
```

Reviewers download the **62 `.txt` files** from Harvard Dataverse (links below) into the folder named in Step 1.

---

## How to Set Up the Project

### Step 1: Download the Data

Download the two datasets from Harvard Dataverse:

| Dataset                     | Link                                                                                                      |
|-----------------------------|-----------------------------------------------------------------------------------------------------------|
| Telecom activity (62 files) | https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/EGZHFV                         |
| Milan Grid                  | https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/QJWLFU                         |

Place the files in these folders:

```
formative_1/
├── Telecommunications - SMS, Call, Internet - MI/   (all 62 .txt files)
├── milano-grid/
│   └── milano-grid.geojson
```

### Step 2: Create a Virtual Environment

Open a terminal in the project folder and run:

**Windows:**

```bash
py -3.13 -m venv .venv
.venv\Scripts\activate
```

---

## Project Structure

```
formative_1/
│
├── formative_1.ipynb          # Main notebook with all code
├── README.md                  # This file
│
├── Telecommunications - SMS, Call, Internet - MI/
│   ├── sms-call-internet-mi-2013-11-01.txt
│   ├── sms-call-internet-mi-2013-11-02.txt
│   └── ... (62 files total)
│
├── milano-grid/
│   └── milano-grid.geojson
│
└── processed/                 (created automatically)
    ├── square_totals_2mo.csv
    ├── ts_2weeks_3squares.csv
    ├── ts_full_square_5161.csv
    └── ...
```

---

## References

- **Data:** Barlacchi et al., Scientific Data (2015), Harvard Dataverse
- **Libraries:** pandas, numpy, matplotlib, seaborn, scipy, statsmodels, scikit-learn, tensorflow

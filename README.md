# 🏟️⚽ Football Scraper

## 🚀 Introduction

This is a simple yet modular Python-based **data pipeline** designed to scrape **football data** from the web. The goal is to gather various football metrics for the **top 5 European leagues**, including:

- ✅ League Standings  
- ❌ Top Goal Scorers  
- ❌ Top Assists  
- ❌ Top Passers  
- ❌ Most Shots on Target  

The current version scrapes data from [twtd.co.uk](https://www.twtd.co.uk) for a specified **match date**, transforms it, and stores the result in a local **CSV file**.

---

## 🛠️ Dependencies

The script uses the following Python modules:

- `os` – for path and file operations  
- `datetime` – to handle date formatting  
- `pandas` – for dataframe creation and manipulation  
- `dotenv` – to manage environment variables  
- `selenium` – to automate web scraping  
- `logging` – for runtime logs and error tracking  

Install all dependencies using:

```bash
pip install -r requirements.txt
```

---

## 🧱 Code Blocks

The script is divided into modular components for clarity and reusability:

### 📝 Logger

Creates a **logging system** to track messages, warnings, and errors. All logs are written to a file within a dedicated `log/` directory.

### ⚙️ Config

Loads and initializes **environment variables** (via `.env`) that are needed to access, store, or process data.

### 🌐 Webpage Loader

Uses **Selenium Chrome WebDriver** to open the webpage dynamically based on a match date provided.

### 🪟 Popup Handler

Closes any **unexpected pop-ups** or cookie banners using predefined XPath logic.

### 🧪 Data Extractor

Extracts football-related stats using **XPath selectors**. The data is parsed from HTML and stored as a list of lists.

### 🔄 Data Transformer

Converts the raw list data into a **Pandas DataFrame**, cleaning and reshaping as needed. Adds a `match_date` column to enrich the dataset.

### 💾 Data Loader

Saves the final dataset to a **CSV file** locally (additional formats like JSON or Parquet planned for future versions).

---

## 📚 Lessons Learnt / Future Developments

Every good software project has a roadmap for improvement. Here are a few enhancements planned for this scraper:

- 🔥 **Exception Handling** – Improve the error-handling pipeline and make logging more robust.
- 🧾 **Additional File Formats** – Add support for saving data in JSON, Parquet, and text formats.
- 📊 **More Data Points** – Scrape additional stats like assists, yellow/red cards, and player performance.
- 🧠 **Type Hints** – Apply consistent Python type hints across the codebase to improve code readability and IDE support.
- ⏰ **Scheduling / Orchestration** – Automate scraper execution weekly using schedulers like cron, Airflow, or Prefect.
- 🧪 **Unit Testing** – Add test coverage using `unittest` or `pytest` for key modules and functions.

---

## 🏁 Conclusion

This project showcases how to architect a **modular and scalable scraping pipeline** using Python, Selenium, and Pandas. It emphasizes reusability and separation of concerns, and is built with growth in mind.

If extended further, the pipeline has the potential to evolve into a **production-grade data service** for football statistics.

> 💡 By adhering to SOLID principles and clean coding patterns, this scraper can evolve in any direction — with minimal refactoring effort.

---

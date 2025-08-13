# 🚀 Optimizing High-Performance Data Processing for Large-Scale Web Crawlers

This project demonstrates a complete pipeline for scraping, cleaning, and processing large-scale web data. The system was designed to crawl over **100,000 news articles** from the New Straits Times (NST) and then benchmark the performance of modern data processing libraries against traditional methods.
<br><br>

### ✨ Features
- **Asynchronous Web Scraping**: Developed a high-performance scraper using **Playwright** and **Asyncio** to concurrently collect **110,642** news articles.
- **Data Extraction**: Parses HTML to extract structured data including Title, URL, Teaser, and Category for each article.
- **Comprehensive Data Cleaning**: A robust data cleaning and transformation pipeline to handle duplicates, missing values, and standardize text data (e.g., location names).
- **Performance Benchmarking**: Systematically evaluates and compares the performance of **Pandas**, **Polars**, and **Modin** across various data processing tasks.
- **Performance Metrics**: Measures and analyzes processing time, CPU usage, memory usage, and throughput (records/sec).
<br>

### 🛠️ Technical Overview
- **Language**: Python
- **Environment**: Google Colab
- **Web Scraping**: Playwright, BeautifulSoup, Asyncio
- **Data Processing & Analysis**: Pandas (baseline), Polars (multi-threaded), Modin (parallel processing)
- **Utilities**: Psutil (for performance monitoring)
<br>

### 📁 File Structure

- **Code Notebooks**:
  - `main_crawler.ipynb`: The main Jupyter Notebook used to run the asynchronous web scraper and collect over 110,000 news articles from the New Straits Times.
  - `clean_data.ipynb`: A notebook dedicated to the data cleaning and transformation pipeline, preparing the raw scraped data for analysis.
  - `optimize_pipeline.ipynb`: Contains the code for the core performance benchmark tests, comparing Pandas, Polars, and Modin across various data processing tasks.
  - `evaluation_charts.ipynb`: A notebook used to generate the final performance comparison charts and visualizations from the benchmark results.
<br>

- **Data & Results**:
  - `/data/NST_News_Articles.xlsx`: The raw, unprocessed dataset scraped from the website, stored in an Excel file.
  - `/data/cleaned_data.zip`: The final cleaned and standardized dataset, compressed into a ZIP file due to its size.
  - `performance_before.csv`: CSV file storing the raw performance metrics from the baseline (Pandas) processing tasks.
  - `performance_after.csv`: CSV file storing the raw performance metrics from the optimized (Polars, Modin) processing tasks.
<br>

- **Documentation**:
  - `Report.pdf`: The comprehensive academic report detailing the project's architecture, methodology, findings, and conclusion.
  - `PresentationSlides.pptx`: The slides used for the final project presentation.
<br>

### 🚀 Getting Started

1.  **Clone the Repository**:
    ```sh
    git clone [your-repo-link]
    cd your-repo-folder
    ```

2.  **Set Up Environment**:
    It is recommended to use Google Colab to run the notebooks.

3.  **Install Dependencies**:
    Run the following command in a notebook cell to install the required libraries:
    ```sh
    pip install pandas polars "modin[ray]" playwright beautifulsoup4 asyncio psutil matplotlib seaborn openpyxl
    # Install browser binaries for Playwright
    playwright install
    ```

4.  **Run the Notebooks**:
    Execute the notebooks in the following order:
    1.  `main_crawler.ipynb` to scrape the data from the NST website. This will generate the raw dataset.
    2.  `clean_data.ipynb` to process and clean the raw data.
    3.  `optimize_pipeline.ipynb` to run the performance comparisons between Pandas, Polars, and Modin.
<br>

### 📊 Dataset Information
- **Target Website:** New Straits Times (NST) News
- **URL:** https://www.nst.com.my/news/
- **Records Collected:** 110,642 articles
- **Data Fields Scraped:** Title, URL, Teaser, Category
<br>

### 🔍 Processing Steps
1.  **Web Scraping**: An asynchronous scraper built with Playwright navigates through four news categories (Nation, Politics, Crime & Courts, Government/Public Policy) on the NST website, collecting article data in parallel to maximize efficiency.
2.  **Data Cleaning**: The raw data is processed to remove duplicate entries and handle missing values in key columns.
3.  **Data Transformation**: Text data, such as location names, is standardized by converting to uppercase, splitting compound entries, removing non-alphabetic characters, and correcting common variations. The article date is also extracted from the URL.
4.  **Performance Evaluation**: The cleaned dataset is run through an identical set of processing tasks using three different libraries:
    - **Pandas**: Serves as the single-threaded baseline.
    - **Polars**: A high-performance library using a Rust backend and multi-threading.
    - **Modin**: A library that scales Pandas workflows by using a parallel processing backend like Ray.
<br>

### 📈 Performance Highlights

The performance evaluation demonstrated the significant advantages of modern parallel processing libraries for large-scale data tasks.

**Key Finding:** **Polars** was the most performant library overall, delivering the **fastest processing time** and **highest throughput** with the **lowest CPU usage**, making it the superior choice for this single-node, high-performance task.
<br><br>

### 🔗 Assignment Source
This project was developed as part of the High Performance Data Processing course. The original assignment instructions and source repository with complete source code, data, and additional documentation can be found here:
- [*Link to Original Project Repo*](https://github.com/kohxuan/HPDP/tree/main/2425/project/p1/GroupE)
<br>

### 🤝 Team: Group E

| Name                                        | Matric No. | GitHub Profile                                         |
| :------------------------------------------ | :--------- | :----------------------------------------------------- |
| Danial Harriz Bin Mohd Asineh @Mohd Asneh | A22EC0152  | [`@danialharriz`](https://github.com/danialharriz)       |
| Chai Yu Tong                                | A22EC0145  | [`@Yutongchai`](https://github.com/Yutongchai)      |
| Koh Su Xuan                                 | A22EC0060  | [`@kohxuan`](https://github.com/kohxuan)               |
| Tiew Chuan Rong                             | A22EC0112  | [`@tiewrong`](https://github.com/tiewrong) |
<br>

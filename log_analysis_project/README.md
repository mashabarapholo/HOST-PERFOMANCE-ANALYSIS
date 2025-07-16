# Proactive Host Failure Detection Analysis

## Project Overview

This project is a data-driven analysis aimed at proactively identifying underperforming or "bad" hosts from server log data. The goal is to move beyond simple failure detection and use statistical analysis and pattern recognition to flag hosts that exhibit signs of instability *before* they cause a critical outage. This workflow was developed in a Jupyter Notebook using Python and popular data analysis libraries.

## Key Features

- **Data Parsing and Cleaning:** Ingests raw log data from a `.csv` file into a structured Pandas DataFrame.
- **Statistical Analysis:** Calculates key performance metrics for each host, including:
    - Success & Failure Rates
    - Average Response Time
    - Standard Deviation of Response Time (to measure consistency)
- **Pattern Detection:** Implements a custom algorithm to detect critical patterns of consecutive 5xx server errors.
- **Data Visualization:** Uses Matplotlib and Seaborn to create clear, professional visualizations that communicate host performance and support data-driven recommendations.

## Tech Stack

- **Language:** Python 3.11
- **Libraries:**
    - **Pandas:** For data manipulation and analysis.
    - **NumPy:** For numerical operations.
    - **Matplotlib & Seaborn:** For data visualization.
- **Environment:** JupyterLab / Jupyter Notebook

## How to Run

1.  Clone this repository: `git clone [your-repo-url]`
2.  Navigate to the project directory: `cd log_analysis_project`
3.  Create and activate a virtual environment:
    ```bash
    python -m venv venv
    source venv/bin/activate  # On macOS/Linux
    # venv\Scripts\activate  # On Windows
    ```
4.  Install the required dependencies:
    ```bash
    pip install pandas numpy matplotlib seaborn jupyterlab
    ```
5.  Launch JupyterLab:
    ```bash
    jupyter lab
    ```
6.  Open the `log-analysis.ipynb` notebook and run the cells.

## Analysis and Findings

The analysis successfully identified `Host C` as the most critical risk. While its failure rate was high, the most significant finding was that it was the only host to exhibit a pattern of **consecutive failures**. This type of behavior is a strong predictor of imminent system failure. The key recommendation from this analysis is to fine-tune monitoring systems to prioritize alerting on consecutive error patterns over simple, isolated failure rates.

*(Optional: You can even embed one of your saved graphs directly into the README!)*
# CAP5619 - Assignment 2: SEC Product Announcement Extraction

## Overview

This project uses Python and the Llama 3.2 language model to identify new product announcements from SEC Form 8-K filings.

The program retrieves filings through the SEC EDGAR API, preprocesses their contents, extracts potential product announcements, and validates the results before exporting them to CSV.

## Implementation

The project was developed in Google Colab using:

- Python
- SEC EDGAR API
- BeautifulSoup
- Ollama with Llama 3.2
- Pandas
- Google Drive for checkpointing and result storage

The extraction process includes keyword-based passage filtering, text chunking, structured JSON responses, evidence validation, and manual review.

## Results

The final analysis processed 100 Form 8-K filings from 10 publicly traded companies.

- 79 product candidates passed automated validation.
- 115 additional extractions were flagged during validation.
- 36 products were accepted after manual review.
- 43 candidates were rejected during manual review.

The final dataset contains five columns:

`company_name`, `stock_name`, `filing_time`, `new_product`, `product_description`

## Files

- **Assignment2.ipynb:** Google Colab notebook containing the extraction pipeline.
- **sec_new_products_final.csv:** Final dataset of 36 accepted products.
- **product_review.csv:** Product candidates, supporting evidence, and manual review decisions.
- **Methodology_Report.pdf:** Explanation of the implementation, challenges, and results.

## Running the Notebook

The notebook is designed for Google Colab.

1. Open the notebook in Google Colab.
2. Configure the SEC request User-Agent and Google Drive output directory.
3. Run the environment setup cells to install dependencies and initialize Ollama.
4. Execute the data collection, preprocessing, extraction, and batch processing sections.
5. Review extracted candidates before generating the final CSV.

The provided final CSV reflects the completed manual review conducted for this assignment.

## Notes

The model runs locally within the Colab runtime through Ollama and does not require a paid LLM API.

Automated validation checks evidence and formatting, but manual review is still necessary to determine whether extracted announcements represent genuinely new products.

# IMDB Top Movies Scraper

This repository contains scripts to scrape top movies from IMDB and save their details in an Excel file.

## Setup

1. Install the required packages:
    ```bash
    pip install xlwt requests lxml beautifulsoup4
    ```

2. Clone the repository and navigate to the project directory:
    ```bash
    git clone <repository-url>
    cd <repository-directory>
    ```

## Files

- `setup_and_imports.py`: Contains the setup and import statements.
- `create_worksheet.py`: Contains the function to create an Excel worksheet.
- `fetch_movie_urls.py`: Contains the function to fetch movie URLs from IMDB.
- `fetch_movie_details.py`: Contains the function to fetch movie details from each movie's page.
- `main.py`: Main script that orchestrates the scraping and saving of movie details.

## Usage

1. Run the `main.py` script to scrape the top movies and save their details into an Excel file:
    ```bash
    python main.py
    ```

2. The output file `topIMDBMovies.xls` will be created in the project directory.

## Example

To fetch movie details for a specific movie, you can use the function from `fetch_movie_details.py`:

```python
from fetch_movie_details import fetch_movie_details

url = 'https://www.imdb.com/title/tt0111161/'
headers = {
    'User-Agent': 'Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36 QIHU 360SE'
}
movie_name, movie_content = fetch_movie_details(url, headers)
if movie_name and movie_content:
    print(f"Movie: {movie_name}\nIntroduction: {movie_content}")

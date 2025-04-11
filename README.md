
Flipkart Iphone Web Scraping


GOAL:

    A multithreaded Python script that scrapes iPhone listings from Flipkart, extracting structured product data including titles, descriptions, prices, ratings, and reviews.
    
Features:

    1. Scrapes product details across multiple pages of Flipkart search results.
    2. Implements multithreading to speed up data extraction.
    3. Extracts and formats product titles, feature descriptions, price, rating and customer reviews.
    4. Includes error handling for missing elements and dynamic structure.
    5. Cleans and formats description content with comma-separated points.
    6. Output-ready for CSV or further analysis.

Approach for the project

    This project follows a modular and efficient approach to scraping structured product data from Flipkart, specifically targeting iPhone listings. Here's a breakdown of the methodology:

    1. Understanding the Flipkart Page Structure
        - Inspected the Flipkart search result pages using browser DevTools.
        - Identified the HTML container (div with class like tUxRFH) that holds individual product cards.
        - Mapped key information fields within each product block:
                Product Title,
                Description (multiple <li> items),
                Price,
                Rating,
                Review count

    2. Web Scraping Setup
        - Used the requests library to make HTTP GET requests with appropriate headers (to mimic a browser and avoid being blocked).
        - Parsed the HTML response using BeautifulSoup with the lxml parser for speed and flexibility.
        - Located and extracted desired HTML elements using class names and tag patterns.

    3. Data Extraction & Cleaning
        - Parsed each product's details by safely navigating nested elements.
        - Handled edge cases where tags might be missing (e.g., NoneType checks).
        - Cleaned the description list into a comma-separated string for readability.
        - Stripped excess whitespace and normalized values for uniformity.

    4. Multithreading for Speed
        - Implemented multithreading using Python’s threading module to scrape multiple pages concurrently.
        - Split the scraping task across threads to significantly reduce runtime when collecting data from multiple pages.
        - Managed thread synchronization and error handling for stability.

    5. Error Handling
        - Wrapped critical sections in try-except blocks to prevent runtime crashes due to missing tags or slow responses.
        - Used conditional checks (if tag:) to ensure no AttributeError occurs when accessing .text.

    6. Output Preparation
        - Stored all extracted data in a list of dictionaries.
        - Designed the output to be easily convertible to CSV, JSON, or Pandas DataFrame for further processing or storage.
        - Example data format includes structured keys: Title, Description, Price, Rating, and Review.

Summary
        
    By combining precise HTML parsing with multithreaded execution, this project efficiently extracts and structures product data from Flipkart while remaining resilient to slight changes in page layout or content.


Technologies: Python, Pandas, BeautifulSoup, Requests, Multi-threading.

Notebook

Link : https://github.com/pheonix2109/FlipkartIphoneWebScraping/blob/main/FlipkartIphonesWebSraping.ipynb

CSV 
Link : https://github.com/pheonix2109/FlipkartIphoneWebScraping/blob/main/flipkart_iphones.csv

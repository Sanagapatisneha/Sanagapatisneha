import requests
from bs4 import BeautifulSoup

# Specify the URL of the website you want to scrape
url = 'intake.steerhealth.io'

# Send a GET request to the URL
response = requests.get(url)

# Parse the HTML content of the website
soup = BeautifulSoup(response.text, 'html.parser')

# Find specific elements on the page using BeautifulSoup's find() or find_all() methods
# For example, to find all <a> tags (hyperlinks) on the page:
links = soup.find_all('a')

# You can then iterate through the found elements and extract the data you need
for link in links:
    # Print the text content of the link
    print(link.text)
    # Print the URL of the link
    print(link.get('href'))

# You can also find other elements like <div>, <p>, <h1>, etc., using similar methods

# Remember to handle exceptions and errors, such as when the website is unreachable or when the element you're looking for doesn't exist

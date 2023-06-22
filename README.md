# Web-scraping

Step 1: Visit the Website
Use automated browsing to visit the Mars news site. Inspect the page to identify which elements to scrape.

Hint To identify which elements to scrape, you might want to inspect the page by using Chrome DevTools.

# Visit the Mars news site: https://static.bc-edx.com/data/web/mars_news/index.html
url = 'https://static.bc-edx.com/data/web/mars_news/index.html'
browser.visit(url)
html = browser.html
Step 2: Scrape the Website
Create a Beautiful Soup object and use it to extract text elements from the website.

# Create a Beautiful Soup object
html_soup = soup(html, 'html.parser')
# Extract all the text elements
all_text = html_soup.find_all('div',class_="list_text")

for texts in all_text:
    print(texts.text) 
November 9, 2022
NASA's MAVEN Observes Martian Light Show Caused by Major Solar Storm
For the first time in its eight years orbiting Mars, NASA’s MAVEN mission witnessed two different types of ultraviolet aurorae simultaneously, the result of solar storms that began on Aug. 27.
Step 3: Store the Results
Extract the titles and preview text of the news articles that you scraped. Store the scraping results in Python data structures as follows:

Store each title-and-preview pair in a Python dictionary. And, give each dictionary two keys: title and preview. An example is the following:

{'title': "NASA's MAVEN Observes Martian Light Show Caused by Major Solar Storm", 
 'preview': "For the first time in its eight years orbiting Mars, NASA’s MAVEN mission witnessed two different types of ultraviolet aurorae simultaneously, the result of solar storms that began on Aug. 27."
}
Store all the dictionaries in a Python list.

Print the list in your notebook.

# Create an empty list to store the dictionaries
store_dict = []
# Loop through the text elements
for texts in all_text:
    
# Extract the title and preview text from the elements
    title = texts.find('div', class_='content_title').text
    preview = texts.find('div', class_='article_teaser_body').text

# Store each title and preview pair in a dictionary
    article_dict = {'Title': title,
                    'Preview': preview }

# Add the dictionary to the list
    store_dict.append(article_dict)
   
article_dict
{'Title': "SAM's Top 5 Discoveries Aboard NASA's Curiosity Rover at Mars",
 'Preview': '“Selfie” of the Curiosity rover with inset showing the SAM instrument prior to installation on the rover.'}
# Print the list to confirm success
store_dict

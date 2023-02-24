# Episode 12: Web Scraping in Python: Tools, Techniques, and Legality
6/5/2020

https://realpython.com/podcasts/rpp/12/
[Kimberly Fessel](http://kimberlyfessel.com/)

- Natural Language Processing (NLP) - anytime working with text data and converting to numbers to be analyzed
    - Combine data from multiple sources to build a picture of customer journey - take info from search patterns and customer reviews and combining into a holistic picture - it did involve web scraping
- Tutorial by Dr. Fessel, "Officially Legal, Let's Scrape the Web"
- Computer Fraud and Abuse Act - used in many cases and possibly with scraping
    - Aimed at hacking behaviors in the 1980s
    - Law used for cyber bullying and viruses
    - Mirky areas with logging in with PW or someone elses PW
- Good projects w/ web scraping
    - Anything - info on the web
    - Tables of sports data, apartment rentals, various text data for NLP projects
    - Have access to all info on the Internet and able to collect in automated way
- Tool of choice
    - Python's request library to get HTML
    - Look at the page itself and use inspect (in the browser) to see what kind of HTML is creating the page
    - [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) for parsing
    - Get body of web page and then ingest into Beautiful Soup
    - Develop strategy to get text that you want
- Techniques for finding data elements that you want
    - Tricky b/c every website is different
    - Two main approaches:
        1. Looking for unique attributes (e.g., HTML IDs assigned to tags, classes). First thing to try is attributes.
        2. Navigate the DOM (i.e., divs, tree w/ parents and children).
- Examples of good sites for practice
    - [boxofficemojo.com](https://www.boxofficemojo.com/) - well structured, most pages look similar to each other
    - wikipedia - good for practice, don't pull too much info at once b/c you can get blocked. Suggest putting in regular pauses to respect the server, you are sending request to server and getting info back. Could get you blocked for being a bully. If you get blocked, you will get error codes. You could get blocked for a day, week, or forever. 
    - [sports-reference.com](https://www.sports-reference.com/) - good sports data.
- Want to save as you go, add in pauses. Every 50 pages write to .csv or save to pickle file.
- Jupyter Notebook - start there for syntax. Usually put into script to run from terminal or elsewhere. Could set up with scheduling.
- Collected info in text format, what happens next?
    - Depends on how you want to use data
    - Convert strings to numbers (int)
    - Might have to strip out text (symbols, spaces, unicode). Use regex, top tool for working with text. Might be able to use Python methods like replace().
    - Dates and times - need to convert in Python to make easier to work with down the road. Python has tools but there are date time packages ([Delorean](https://pypi.org/project/Delorean/), [Maya](https://pypi.org/project/maya/)).
- Dynamic sites require more robust packages - [Selenium](https://www.selenium.dev/)
    - Selenium in original form will launch browser - Chrome driver and can fill in dynamic content
    - Load page with Selenium and then process with Beautiful Soup
    - Can use Selenium to interact with a page (clicking, typing)
- Large scale web scraping project - use [Scrapy](https://scrapy.org/) 
    - Offers cloud services for holding lots of data
    - Useful for indexing various sites
    - Follow lots of links
- Tips and tricks
    - Transform in Pandas - find and replace
    - Pivot tools

*Python Pizza conference ([Hamburg GE](https://hamburg.python.pizza/))
* PyCon, ODSC East, PyOhio - look for talks, can check Dr. Fessel's blog
* Real Python has request package tutorial. Request is a python package for requesting data through API and as a scraper.

Useful links:
- [Tutorial: It's Officially Legal So Let's Scrape The Web](https://www.youtube.com/watch?v=RUQWPJ1T6Zc)
- [Computer Fraud and Abuse Act](https://en.wikipedia.org/wiki/Computer_Fraud_and_Abuse_Act)
- [Jupyter Notebook: An Introduction](https://realpython.com/jupyter-notebook-introduction/)
- [The Python pickle Module: How to Persist Objects in Python](https://realpython.com/python-pickle-module/)
- [Beautiful Soup: Build a Web Scraper with Python](https://realpython.com/beautiful-soup-web-scraper-python/)
- [Making HTTP Requests with Python](https://realpython.com/courses/python-requests/)
- [Natural Language Processing with spaCy in Python](https://realpython.com/natural-language-processing-spacy-python/)
- [Regular Expressions: Regexes in Python (Part1)](https://realpython.com/regex-python/)
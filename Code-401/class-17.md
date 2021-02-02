# Class 17: Web Scraping

## [Web Scrape with Python in 4 minutes](https://towardsdatascience.com/how-to-web-scrape-with-python-in-4-minutes-bc49186a8460)

**Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.**

When you begin you have to have access to the websites `turnstile` data.

> Example from the article:
> 
> `http://web.mta.info/developers/turnstile.html`

Depending upon the website they may have varying intervals at which they compile data. The example from the article has data that is compiled every week.


> ## <u>Important notes about web scraping:</u>
> 
> ## ***Read through the website’s Terms and Conditions to understand how you can legally use the data. Most sites prohibit you from using the data for commercial purposes.***
>
>  <br> 
>
> ## ***Make sure you are not downloading data at too rapid a rate because this may break the website. You may potentially be blocked from the site as well.***

## Inspecting the Website

- Step 1: Figure out where you can locate the links to the files you want to download inside the multiple levels of HTML tags.
        
    - Start by inspecting the page to see what `HTML` tags you can find 
    - Use the highlighter to assist in finding this information. ![highlighter photo](https://miro.medium.com/max/30/1*OBTSehekWVX6rSXUaibd1A.png)
    - Once you've found the location of the links you can start writing your code.

## Python Code

Libraries you will want to import:

- `import requests`
- `import urllib.request`
- `import time`
- `from bs4 import BeautifulSoup`

Set the URL to the website and access the site with your requests library.

```
url = 'http://web.mta.info/developers/turnstile.html'
response = requests.get(url)
```
If the access was successful, you should see the following output:
```
Input: response
Output: <Response [200]>
```
> Response 200 means that the access request went through

Next, parse the html with [BeautifulSoup](https://www.crummy.com/software/BeautifulSoup/bs4/doc/) so that you can work with a nicer, nested BeautifulSoup data structure.

```
soup = BeautifulSoup(response.text, “html.parser”)
```

Use the method .findAll to locate all of the `<a>` tags.

```
soup.findAll('a')
```

Next, let’s extract the actual link that we want. Let’s test out the first link.
```
one_a_tag = soup.findAll(‘a’)[38]
link = one_a_tag[‘href’]
```
> In the article the data they were after started on Line 38, hence [38]

The above code block only saves part of the path name:

- Actual Received: `data/nyct/turnstile/turnstile_180922.txt`
- Path Needed: `‘http://web.mta.info/developers/data/nyct/turnstile/turnstile_180922.txt`

Discrepancies like this can be discovered by hovering over the link and allowing the browser to display the pathway of the actual link or clicking the link and looking at the URL bar of that links landing page.

Provide request.urlretrieve with two parameters: file url and the filename. 

```
download_url = 'http://web.mta.info/developers/'+ link
urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:])
```

You should include this line of code so that you can pause our code for a second so that you are not spamming the website with requests. This helps avoid getting flagged as a spammer.

```
time.sleep(1)
```
The code below contains the entire set of code for web scraping the NY MTA turnstile data.(Written by Julia Kho)

```
# Import libraries
import requests
import urllib.request
import time
from bs4 import BeautifulSoup

# Set the URL you want to webscrape from
url = 'http://web.mta.info/developers/turnstile.html'

# Connect to the URL
response = requests.get(url)

# Parse HTML and save to BeautifulSoup object¶
soup = BeautifulSoup(response.text, "html.parser")

# To download the whole data set, let's do a for loop through all a tags
line_count = 1 #variable to track what line you are on
for one_a_tag in soup.findAll('a'):  #'a' tags are for links
    if line_count >= 36: #code for text files starts at line 36
        link = one_a_tag['href']
        download_url = 'http://web.mta.info/developers/'+ link
        urllib.request.urlretrieve(download_url,'./'+link[link.find('/turnstile_')+1:]) 
        time.sleep(1) #pause the code for a sec
    #add 1 for next line
    line_count +=1
```
[GitHub ](https://github.com/julia-git/webscraping_ny_mta)for the code written/described in this article


## [What is Web Scraping?](https://en.wikipedia.org/wiki/Web_scraping)

**Web scraping, web harvesting, or web data extraction is [data scraping](https://en.wikipedia.org/wiki/Data_scraping) used for [extracting data](https://en.wikipedia.org/wiki/Data_extraction) from websites.**

Web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a [bot](https://en.wikipedia.org/wiki/Internet_bot) or [web crawler](https://en.wikipedia.org/wiki/Web_crawler).

Web scraping a web page involves fetching it and extracting from it.

Once fetched, the content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet, or many other needed manipulations to achieve the desired end result.

> Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else.

Many uses of Web scraping:
- **contact scraping** - The practice of obtaining access to a customer's e-mail account in order to retrieve contact information that is then used for marketing purposes.

- **web indexing** - Comprises methods for indexing the contents of a website or of the Internet as a whole. Individual websites or intranets may use a back-of-the-book index, while search engines usually use keywords and metadata to provide a more useful vocabulary for Internet or onsite searching. With the increase in the number of periodicals that have articles online, web indexing is also becoming important for periodical websites.

- **web mining** - The application of data mining techniques to discover patterns from the World Wide Web. As the name proposes, this is information gathered by mining the web. It makes utilization of automated apparatuses to reveal and extricate data from servers and web2 reports, and it permits organizations to get to both organized and unstructured information from browser activities, server logs, website and link structure, page content and different sources.

- **data mining** - Process of discovering patterns in large data sets involving methods at the intersection of machine learning, statistics, and database systems. Data mining is an interdisciplinary subfield of computer science and statistics with an overall goal to extract information from a data set and transform the information into a comprehensible structure for further use. Data mining is the analysis step of the "knowledge discovery in databases" process, or KDD. Aside from the raw analysis step, it also involves database and data management aspects, data pre-processing, model and inference considerations, interestingness metrics, complexity considerations, post-processing of discovered structures, visualization, and online updating.

- **online price change monitoring and price comparison** - A vertical search engine that shoppers use to filter and compare products based on price, features, reviews and other criteria. Most comparison shopping sites aggregate product listings from many different retailers but do not directly sell products themselves, instead earning money from affiliate marketing agreements. There is a huge contribution of comparison shopping websites in the expansion of current E-commerce industry.

- **product review scraping**

- **gathering real estate listings**

- **weather data monitoring**

- **website change detection** - Change detection and notification refers to automatic detection of changes made to World Wide Web pages and notification to interested users by email or other means. Whereas search engines are designed to find web pages, CDN systems are designed to monitor changes to web pages. Before change detection and notification, it was necessary for users to manually check for web page changes, either by revisiting web sites or periodically searching again. Efficient and effective change detection and notification is hampered by the fact that most servers do not accurately track content changes through Last-Modified or ETag headers. A comprehensive analysis regarding CDN systems can be found

- **research**

- **tracking online presence and reputation**

- **web mashup** - A mashup, in web development, is a web page or web application that uses content from more than one source to create a single new service displayed in a single graphical interface. The term mashup originally comes from creating something by combining elements from two or more sources. In recent English parlance it can refer to music, where people seamlessly combine audio from one song with the vocal track from another - thereby mashing them together to create something new.

- **web data integration** - Web data integration (WDI) is the process of aggregating and managing data from different websites into a single, homogeneous workflow. This process includes data access, transformation, mapping, quality assurance and fusion of data. Data that is sourced and structured from websites is referred to as "web data". WDI is an extension and specialization of data integration that views the web as a collection of heterogeneous databases.






## [Track Amazon Prices](https://www.youtube.com/watch?v=Bg9r_yLk7VY)












<br><br><br><br><br><br><br><br><br><br><br><br>

## [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/)

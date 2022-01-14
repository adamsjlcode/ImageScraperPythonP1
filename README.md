# Project One Image Scraper
---
Scraping Is a very essential skill for everyone to get data from any website. In this article, we are going to see how
to scrape images from websites using python. For scraping images, we will try different approaches.

**Method 1:** Using BeautifulSoup and Requests

* [**bs4**](https://www.geeksforgeeks.org/implementing-web-scraping-python-beautiful-soup/)**:** Beautiful Soup(bs4) is
  a Python library for pulling data out of HTML and XML files. This module does not come built-in with Python. To
  install this type the below command in the terminal.

`pip install bs4
`
* [**requests**](https://www.geeksforgeeks.org/python-requests-tutorial/)**:**  Requests allows you to send HTTP/1.1
  requests extremely easily. This module also does not come built-in with Python. To install this type the below command
  in the terminal.

`pip install requests`

**Approach:**

* Import module
* Make requests instance and pass into URL
* Pass the requests into a Beautifulsoup() function
* Use ‘img’ tag to find them all tag (‘src ‘)

**Implementation:**

* Python3

Python3
-------

```
import requests 
from bs4 import BeautifulSoup 
    
def getdata(url): 
    r = requests.get(url) 
    return r.text 
    
htmldata = getdata("https://www.geeksforgeeks.org/") 
soup = BeautifulSoup(htmldata, 'html.parser') 
for item in soup.find_all('img'):
    print(item['src'])
```
**Output:**

> https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201018234700/GFG-RT-DSA-Creative.png  
> https://media.geeksforgeeks.org/wp-content/cdn-uploads/logo-new-2.svg

**Method 2:** Using urllib and BeautifulSoup

[**urllib**](https://www.geeksforgeeks.org/python-urllib-module/) **:** It is a Python module that allows you to access,
and interact with, websites with their URL. To install this type the below command in the terminal.

pip install urllib

**Approach:**

* Import module
* Read URL with urlopen()
* Pass the requests into a Beautifulsoup() function
* Use ‘img’ tag to find them all tag (‘src ‘)

**Implementation:**

* Python3

Python3
-------
```
from urllib.request import urlopen
from bs4 import BeautifulSoup
  
htmldata = urlopen('https://www.geeksforgeeks.org/')
soup = BeautifulSoup(htmldata, 'html.parser')
images = soup.find_all('img')
  
for item in images:
    print(item['src'])
```

**Output:**

> https://media.geeksforgeeks.org/wp-content/cdn-uploads/20201018234700/GFG-RT-DSA-Creative.png  
> https://media.geeksforgeeks.org/wp-content/cdn-uploads/logo-new-2.svg

Attention geek! Strengthen your foundations with the [**Python Programming
Foundation**](https://practice.geeksforgeeks.org/courses/Python-Foundation?utm_source=geeksforgeeks&utm_medium=article&utm_campaign=GFG_Article_Bottom_Python_Foundation)
Course and learn the basics.

To begin with, your interview preparations Enhance your Data Structures concepts with the [**Python
DS**](https://practice.geeksforgeeks.org/courses/Data-Structures-With-Python?utm_source=geeksforgeeks&utm_medium=article&utm_campaign=GFG_Article_Bottom_Python_DS)
Course. And to begin with your Machine Learning Journey, join
the **[Machine Learning - Basic Level Course](https://practice.geeksforgeeks.org/courses/machine-l
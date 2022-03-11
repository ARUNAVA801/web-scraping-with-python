# web-scraping-with-python
# step 0 : get all the requirements 

import requests
from bs4 import BeautifulSoup
url = "https://www.programiz.com/dsa#:~:text=A%20data%20structure%20is%20a,efficient%20and%20optimized%20computer%20programs."
# step 1 : get the html
r = requests.get(url)
HtmlContent = r.content
# print(HtmlContent)
# step 2 : parse the html
soup = BeautifulSoup(HtmlContent, 'html.parser')
# print(soup.prettify)
# step 3 : html tree traversal 
# commonly used type of objects : 
# print(type(title)) 1.tag
#  print(type(title.string)) 2.navigable
#  print(type(soup)) 3.BeautifulSoup
# 4. comment 
# get the title of the html page
title = soup.title
print(title.string)
# paras = soup.find_all('p')
# print(paras)

# to get all the anchosrtags
# anchors = soup.find_all('a')
# print(anchors)
# get first element
# print(soup.find('p')['class'])
# print(soup.find_all('p, class_="section'))
# to get all the text 
# print(soup.find('p').getText())

print(soup.getText())

# Python_Project-3
#News Article by BeautifulSoup


import requests
from bs4 import BeautifulSoup

url = 'https://timesofindia.indiatimes.com/world/pakistan/pakistan-punjab-govt-stops-arrears-time-scale-payments-to-employees-officers-amid-financial-crisis/articleshow/100072521.cms'

r = requests.get(url)

scop  = BeautifulSoup(r.content, 'html.parser')

Article_Title = scop.find('h1', {'class' : 'HNMDR'})

Article_Content = scop.find('div', {'class' : '_s30J clearfix'})

Article_Author_and_Date = scop.find('div', {'class' : 'xf8Pm byline'})

print(Article_Title.text)
print(Article_Content.text)
print(Article_Author_and_Date.text)

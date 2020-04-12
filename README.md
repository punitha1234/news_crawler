# news_crawler
#import BeautifulSoup from bs4 module
from bs4 import BeautifulSoup
#import requests
import requests
#get the desired url to perform crawing
content=requests.get('https://economictimes.indiatimes.com/headlines.cms')
#creating an soup object
soup=BeautifulSoup(content.text,'lxml')
news=soup.find('h2',{'class':'headings'})
print(news.span.string)
new1=soup.find('ul',{'class':'headlineData'})
for new11 in new1:
	links=new11.find_all('a')
	for link in links:
		print(link.text)
		print()   

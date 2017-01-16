from urllib.request import urlopen
from bs4 import BeautifulSoup
import requests
import re

URL = "http://daily.zhihu.com/"

def get_url(URL):
    bsobj = urlopen(URL)
    text = bsobj.read().decode("utf-8")
    return text

def get_reg(bsobj):
    html = str(bsobj)
    reg_url = re.compile(r'<a href="/story/(.*?)" class="link-button">')
    items = re.findall(reg_url, html)
    urls = []
    for item in items:
        urls.append("http://daily.zhihu.com/story/" + item)
    return urls

def get_contect(url):
    html = get_url(url)
    pattern = re.compile('<h1 class="headline-title">(.*?)</h1>')
    items = re.findall(pattern, html)
    print("**" + items[0] + "**")
    pass#需要写正则表达式获取正文内容


html = get_url(URL)
urls = get_reg(html)
for url in urls:
    try:
        get_contect(url)
    except:
        print("出错了")
        break

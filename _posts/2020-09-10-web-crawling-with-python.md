---
title: "WEB CRAWLING WITH PYTHON"
date: 2020-09-10 10:45:00 -0400
categories: crawling
---

# Web Crawling with Python

## Web Crawling vs. Web Scraping (크롤링, 스크래핑 차이)
> **Web crawling** is a way to get the information and organise it, while **web scraping** can get very specific data and store it for later use. Web scraping is about downloading structured data from web, selecting some of that data, and passing along what you selected to another process. 
**크롤러**란 조직적, 자동화된 방법으로 월드와이드 웹을 탐색하는 컴퓨터 프로그램(위키백과)
**크롤링**은 크롤러가 하는 작업을 부르는 말로, 여러 인터넷 사이트의 페이지를 수집해서 분류하는 것. 대체로 인덱싱하고 DB에 저장하는 과정까지 포함.
**스크래핑**이란 HTTP를 통해 웹 사이트의 내용을 긁어다 원하는 형태로 가공하는 것. 크롤링 agent와 parser까지 포함하는 개념이라고 보면 됨.

## Web Crawling Libraries
1. Urllib: Python package that collects several modules for working with URLs. It defines functions and classes to help in URL actions.
파이썬의 표준 라이브러리로, URL 관련 라이브러리라는 의미의 패키지. URL 문자열과 웹 요청에 관련된 모듈 5개를 제공.

```python
urllib.request # URL 문자열을 가지고 요청 기능 제공
urllib.response # urllib 모듈에 의해 사용되는 응답 기능 관련 클래스들 제공
urllib.parse # URL 문자열을 파싱하여 해석하는 기능 제공
urllib.error # urllib.request에 의해 발생하는 예외 클래스들 제공
urllib.robotparser # robots.txt 파일을 구문 분석하는 기능 제공
```

* urllib.request module: helps to define functions and classes to open URLs (mostly HTTP)
> URL 문자열을 가지고 HTTP 요청을 수행. urlopen() 함수를 사용하여 웹 서버에 페이지를 요청하고, 서버로부터 받은 응답을 저장하여 응답 객체(http.client.HTTPResponse)를 반환. http.client.HTTPResponse 클래스는 웹 서버로부터 받은 응답을 래핑하는 객체로, 응답 헤더나 바디의 내용을 추출하는 메서드를 제공.
```python
import urllib.request
request_url = urllib.request.urlopen('your_url')
print(request_url.read()) # prints the source code of the URL.
```

http.client.HTTPResponse 객체의 read() 메서드를 실행하여 웹 서버가 전달한 데이터(응답 바디)를 바이트 열로 읽어 들임.
웹 서버가 한글을 포함한 텍스트 형식의 HTML 문서를 읽을 때에는 텍스트 형식으로 변환 -> read().decode('utf-8')
크롤링하려는 웹 페이지가 어떠한 문자 셋으로 작성되었는지 파악하려면 소스에서 <meta> 태그의 charset 정보를 체크하면 됨.
혹은, 파이썬 프로그램으로도 파악할 수 있음. http.client.HTTPResponse객체의 info() 메서드를 호출하면 http.client.HTTPMessage 객체가 리턴 됨.
웹 서버로부터 전달되는 Content-Type이라는 응답 헤더 정보를 읽고 해당 페이지의 문자 셋 정보를 추출해 줌 (encoding = doc.info().get_content_charset())

* urllib.parse module: helps to define


## Solutions When Blocked (TimeoutException)

As I was crawling, I caught TimeoutException with "Message: timeout: Timed out receiving message from renderer". 

Here is a list of solutions that I've searched and tried to solve this timeout . (Selenium, Chrome)




1. Set header (User-Agent)

> The server could consider your web crawler as something malicious, as if a hacking bot. So they might want to stop giving you the information you requested anymore. In this case, you can tell them, "I'm not a bot, but a human...I think." You can do this by putting *User-Agent* in *headers*. Here, *header* contains information about you (or your program) who accesses the site. 



Here is my original code.

```python
driver = webdriver.Chrome(executable_path=r"your_chromecdriver_path")
```



Here is the new code with User-Agent information added.

```python
chrome_options = webdriver.ChromeOptions()
chrome_options.add_argument('--user-agent="Mozilla/5.0 (Macintosh; Intel Mac OS X 10_14_1) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/85.0.4183.83 Safari/537.36"')
driver = webdriver.Chrome(chrome_options=chrome_options, executable_path=r"your_chromedriver_path")
```

You can get your own User-Agent information in this site: http://www.useragentstring.com/. Just copy and paste the User Agent String, because it contains Chrome already. Or you can search for a specific brower you want by clicking 'List of User Agent Strings'.




2. Loop and Break

> The server can get overloaded by your scraper, especially when their websites are slow or small. Even on large websites, timeouts are common for various reasons, including the one mentioned earlier. You can add loop and break if you want to pass that page when it took too long. 



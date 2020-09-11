---
title: "WEB CRAWLING WITH PYTHON"
date: 2020-09-10 10:45:00 -0400
categories: crawling
---

# Web Crawling with Python

(to be updated)



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


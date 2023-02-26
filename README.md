# QA-testing-project
This is a QA testing project for an e-commerce application with special focus on general test cases , Product Buy Flow and user registration. The goal is to ensure that the application meets all functional requirements, is user-friendly, performs well under various conditions, and is secure for its users.


In order to execute the same, this project involves the usage of Selenium Webdriver. Selenium WebDriver is a popular open-source tool for automating web browsers. It provides a programming interface to automate web browsers and perform various actions like filling out forms, clicking buttons, navigating pages, and scraping web data.

Selenium WebDriver supports multiple programming languages such as Java, Python, C#, Ruby, and JavaScript. It is used in various applications, such as web testing, web scraping, and automation.

Selenium WebDriver can be used with various testing frameworks like JUnit, TestNG, NUnit, and Pytest to create robust and reliable automated tests. It is a powerful tool that can help save time and effort in testing and web automation.



How to obtain the page title using Selenium webdriver? page title of amazon ,facebook ,tutorialspoint...any one

To obtain the page title using Selenium Webdriver we use the following:

from selenium.webdriver.chrome.service import Service
from selenium import webdriver

service = Service(executable_path="C:\Program Files\chromedriver.exe")
driver = webdriver.Chrome(service=service)

from selenium import webdriver

# Navigate to the desired page
driver.get('https://www.youtube.com/watch?v=Xjv1sY630Uc&ab_channel=TechWithTim%27)

# Get the page title
page_title = driver.title

# Print the page title
print(page_title)

# Close the WebDriver instance
driver.quit()

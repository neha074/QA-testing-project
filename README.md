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



I.
For any ecommerce application there are n number of test cases that has to be considered for its fullest efficiency and working.
For example for an ecommerce website the test cases include :

Registration and Login: Ensure that users can register and log in to the ecommerce application without any issues. Check that the user's personal details are captured accurately, and authentication and authorization are functioning correctly.

Product search and selection: Test the functionality of the product search bar and ensure that it displays relevant results for user queries. Verify that users can select products and add them to the shopping cart without any issues.

Shopping Cart: Test the functionality of the shopping cart, including adding, editing, and removing products, as well as calculating totals and taxes accurately.

Payment processing: Test the payment gateway functionality and ensure that payments are processed securely and efficiently. Check for errors or delays in processing payments and verify that user payment information is stored securely.

Order tracking: Test the order tracking functionality and ensure that users can track their orders, view order history, and receive notifications of order status changes.

Shipping and delivery: Test the shipping and delivery process and ensure that the application can handle various shipping options, delivery addresses, and delivery timeframes. Verify that shipping costs are calculated correctly, and shipping information is accurately displayed to the user.

Customer support: Test the customer support functionality, including chatbots, customer service emails, and phone support. Verify that customer service requests are routed to the correct department, and customers receive prompt and helpful responses.

In this project i've used the following general test cases for an ecommerce application

initially we import the selenium webdriver 

1. To view a particular item, and get glimpse of their pictures
2. Add the quantity of the items
3. Selecting the date of order of item
4. Checking out the item
5. Right after checking out activating the registration and fetching details of the user like their name , email, address , city country etc 
6. Accepting the terms and conditions and receiving the successful completion of the order

II. PRODUCT BUY FLOW

1. we include the URL of the particular website right after initializing webdriver
2. we search the element that we need to buy
3. view the item and their pictures
4. include the quantity of the item
5. adding the item to the cart
6. selecting or choosing other item that we need to buy and adding the same into the cart
7. selecting checkout
8. filling the details of the customer which includes the
    1. Name
    2. email
    3. phone no
    4. address
    5. city
    6. postcode
    7. country
    8. region
9. Accepting the terms and conditions
10. final price of the selected products
11. confirming the order
12. successful completion of the order


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

SAMPLE TEST CASES:
from selenium.webdriver.chrome.service import Service
from selenium import webdriver

service = Service(executable_path="\chromedriver.exe")
driver = webdriver.Chrome(service=service)

from selenium.webdriver.common.keys import Keys
import time
import random
from selenium.webdriver import ActionChains
from selenium.webdriver.support.select import Select
from selenium.webdriver.common.by import By


#initialize webdriver

driver=webdriver.Chrome('C:/bin/chromedriver3.exe')

#Open URL and maximize window

driver.get('http://tutorialsninja.com/demo/')
driver.maximize_window()
time.sleep(1)

#phones button

phones=driver.find_element(By.LINK_TEXT,'Phones & PDAs')
#phones=driver.find_element(By.XPATH,'//a[text()="Phones & PDAs"]')
phones.click()
time.sleep(1)

#iphone

#iphone=driver.find_element(By.XPATH,'//a[text()="iPhone"]')
iphone=driver.find_element(By.LINK_TEXT,'iPhone')
iphone.click()
time.sleep(1)

#first picture

first_pic=driver.find_element(By.XPATH,'//ul[@class="thumbnails"]/li[1]')
first_pic.click()
time.sleep(1)

#next picture

next_click=driver.find_element(By.XPATH,'//button[@title="Next (Right arrow key)"]')

for i in range(0,5):
    next_click.click()
    time.sleep(1)

#save screenshot

driver.save_screenshot('screenshot#' + str(random.randint(0,101)) + '.png')
time.sleep(1)

#close

x_button=driver.find_element(By.XPATH,'//button[@title="Close (Esc)"]')
x_button.click()
time.sleep(1)

#quantity

quantity=driver.find_element(By.ID,'input-quantity')
quantity.click()
time.sleep(1)

quantity.clear()
time.sleep(1)
quantity.send_keys('2')
time.sleep(1)

#add to cart

add_to_button=driver.find_element(By.ID,'button-cart')
#add_to_button.click()
time.sleep(1)

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

SAMPLE TEST CASES

#Open URL and maximize window

driver.get('http://tutorialsninja.com/demo/')
driver.maximize_window()
time.sleep(1)

#phones button

phones=driver.find_element(By.LINK_TEXT,'Phones & PDAs')
#phones=driver.find_element(By.XPATH,'//a[text()="Phones & PDAs"]')
phones.click()
time.sleep(1)

#iphone

#iphone=driver.find_element(By.XPATH,'//a[text()="iPhone"]')
iphone=driver.find_element(By.LINK_TEXT,'iPhone')
iphone.click()
time.sleep(1)

#first picture


first_pic=driver.find_element(By.XPATH,'//ul[@class="thumbnails"]/li[1]')
first_pic.click()
time.sleep(1)

#next picture

next_click=driver.find_element(By.XPATH,'//button[@title="Next (Right arrow key)"]')

for i in range(0,5):
    next_click.click()
    time.sleep(1)

#save screenshot

driver.save_screenshot('screenshot#' + str(random.randint(0,101)) + '.png')
time.sleep(1)

#close

x_button=driver.find_element(By.XPATH,'//button[@title="Close (Esc)"]')
x_button.click()
time.sleep(1)

#quantity

quantity=driver.find_element(By.ID,'input-quantity')
quantity.click()
time.sleep(1)

quantity.clear()
time.sleep(1)
quantity.send_keys('2')
time.sleep(1)

#add to cart

add_to_button=driver.find_element(By.ID,'button-cart')
#add_to_button.click()
time.sleep(1)


laptops=driver.find_element(By.XPATH,'//a[text()="Laptops & Notebooks"]')
action=ActionChains(driver)
action.move_to_element(laptops).perform()
time.sleep(1)
laptops_2=driver.find_element(By.XPATH,'//a[text()="Show All Laptops & Notebooks"]')
laptops_2.click()
time.sleep(1)

#click on HP laptop

HP=driver.find_element(By.XPATH,'//a[text()="HP LP3065"]')
HP.click()

#scroll

add_to_button_2=driver.find_element(By.XPATH,'//button[@id="button-cart"]')
add_to_button_2.location_once_scrolled_into_view
time.sleep(1)

#calendar

calendar=driver.find_element(By.XPATH,'//i[@class="fa fa-calendar"]')
calendar.click()
time.sleep(1)

next_click_calendar=driver.find_element(By.XPATH,'//th[@class="next"]')
month_year=driver.find_element(By.XPATH,'//th[@class="picker-switch"]')

#year:2023 month:february
while month_year.text != 'February 2023':
    next_click_calendar.click()
time.sleep(1)

#day 26
calendar_date=driver.find_element(By.XPATH,'//td[text()="26"]')
calendar_date.click()
time.sleep(1)

#add to button

add_to_button_2.click()
time.sleep(1)

#Checkout

go_to_cart=driver.find_element(By.ID,'cart-total')
go_to_cart.click()
time.sleep(1)

checkout=driver.find_element(By.XPATH,'//p[@class="text-right"]/a[2]')
checkout.click()
time.sleep(1)

#click on guest account

guest=driver.find_element(By.XPATH,'//input[@value="guest"]')
guest.click()

#click continue 1
continue_1=driver.find_element(By.ID,'button-account')
continue_1.click()
time.sleep(1)

#scrolling
step_2=driver.find_element(By.XPATH,'//a[text()="Step 2: Billing Details "]')
step_2.location_once_scrolled_into_view
time.sleep(1)

#first name

first_name=driver.find_element(By.ID,'input-payment-firstname')
first_name.click()
time.sleep(1)
first_name.send_keys('neha')
time.sleep(1)

#last_name

last_name=driver.find_element(By.ID,'input-payment-lastname')
last_name.click()
time.sleep(1)
last_name.send_keys('MA')
time.sleep(1)

#email

email=driver.find_element(By.ID,'input-payment-email')
email.click()
time.sleep(1)
email.send_keys('nehamanickam74@gmail.com')
time.sleep(1)

#telephone

telephone=driver.find_element(By.ID,'input-payment-telephone')
telephone.click()
time.sleep(1)
telephone.send_keys('9884615864')
time.sleep(1)

#address

address=driver.find_element(By.ID,'input-payment-address-1')
address.click()
time.sleep(1)
address.send_keys('teststreet 187')
time.sleep(1)

#city

city=driver.find_element(By.ID,'input-payment-city')
city.click()
time.sleep(1)
city.send_keys('Chennai')
time.sleep(1)

#postcode

postcode=driver.find_element(By.ID,'input-payment-postcode')
postcode.click()
time.sleep(1)
postcode.send_keys('600095')
time.sleep(1)


#country

country=driver.find_element(By.ID,'input-payment-country')
dropdown_1=Select(country)
time.sleep(1)
dropdown_1.select_by_index(106)
time.sleep(1)

#region

region=driver.find_element(By.ID,'input-payment-zone')
dropdown_2=Select(region)
time.sleep(1)
dropdown_2.select_by_visible_text('Tamil Nadu')
time.sleep(1)

#click continue 2

continue_2=driver.find_element(By.XPATH,'//input[@id="button-guest"]')
continue_2.click()
time.sleep(1)

#click continue 3

continue_3=driver.find_element(By.XPATH,'//input[@id="button-shipping-method"]')
continue_3.click()
time.sleep(1)

#accept terms & conditions

t_e=driver.find_element(By.XPATH,'//input[@name="agree"]')
t_e.click()
time.sleep(1)

#click continue 4

continue_4=driver.find_element(By.XPATH,'//input[@id="button-payment-method"]')
continue_4.click()
time.sleep(1)

#final price

final_price=driver.find_element(By.XPATH,'//table[@class="table table-bordered table-hover"]/tfoot/tr[3]/td[2]')

print("The final price of both products is " + final_price.text)
time.sleep(1)

#click on the confirmation button

confirmation_button=driver.find_element(By.ID,'button-confirm')
confirmation_button.click()
time.sleep(1)


#success text

success_text=driver.find_element(By.XPATH,'//div[@class="col-sm-12"]/h1')
print(success_text.text)
time.sleep(1)

driver.close()



III. USER REGISTRATION

At the end of checking out the details of the user is prompted which includes the following
    1. First Name and last name
    2. email
    3. phone no
    4. address
    5. city
    6. postcode
    7. country
    8. region
    
   SAMPLE TEST CASES
   
    #click on guest account
   
guest=driver.find_element(By.XPATH,'//input[@value="guest"]')
guest.click()

#click continue 1

continue_1=driver.find_element(By.ID,'button-account')
continue_1.click()
time.sleep(1)

#scrolling

step_2=driver.find_element(By.XPATH,'//a[text()="Step 2: Billing Details "]')
step_2.location_once_scrolled_into_view
time.sleep(1)

#first name

first_name=driver.find_element(By.ID,'input-payment-firstname')
first_name.click()
time.sleep(1)
first_name.send_keys('neha')
time.sleep(1)

#last_name

last_name=driver.find_element(By.ID,'input-payment-lastname')
last_name.click()
time.sleep(1)
last_name.send_keys('MA')
time.sleep(1)

#email

email=driver.find_element(By.ID,'input-payment-email')
email.click()
time.sleep(1)
email.send_keys('nehamanickam74@gmail.com')
time.sleep(1)

#telephone

telephone=driver.find_element(By.ID,'input-payment-telephone')
telephone.click()
time.sleep(1)
telephone.send_keys('9884615864')
time.sleep(1)

#address

address=driver.find_element(By.ID,'input-payment-address-1')
address.click()
time.sleep(1)
address.send_keys('teststreet 187')
time.sleep(1)

#city

city=driver.find_element(By.ID,'input-payment-city')
city.click()
time.sleep(1)
city.send_keys('Chennai')
time.sleep(1)

#postcode

postcode=driver.find_element(By.ID,'input-payment-postcode')
postcode.click()
time.sleep(1)
postcode.send_keys('600095')
time.sleep(1)


#country

country=driver.find_element(By.ID,'input-payment-country')
dropdown_1=Select(country)
time.sleep(1)
dropdown_1.select_by_index(106)
time.sleep(1)

#region

region=driver.find_element(By.ID,'input-payment-zone')
dropdown_2=Select(region)
time.sleep(1)
dropdown_2.select_by_visible_text('Tamil Nadu')
time.sleep(1)


SAMPLE SCREENSHOTS

![Screenshot 2023-02-26 132801](https://user-images.githubusercontent.com/113016903/221399171-7d6a4e14-857a-4ec6-967f-e82585afcde5.jpg)




![image](https://user-images.githubusercontent.com/113016903/221399225-92afdfc3-866c-45a3-b313-4f2cc4dfd45d.png)




![image](https://user-images.githubusercontent.com/113016903/221399241-225e4b9c-ede9-48df-9aff-456fec84fba3.png)





![image](https://user-images.githubusercontent.com/113016903/221399263-0f809299-0a76-4273-8ac5-9b563bca0941.png)





![image](https://user-images.githubusercontent.com/113016903/221399276-e7b6971f-2c53-460b-9018-d4ef37c7ced7.png)





![image](https://user-images.githubusercontent.com/113016903/221399307-34ab4ba7-b0eb-4e5c-b2bb-34f1445aa5ad.png)


![image](https://user-images.githubusercontent.com/113016903/221399327-6a5c5cbb-b25b-4007-8d22-d967528ec934.png)


![image](https://user-images.githubusercontent.com/113016903/221399393-573fd166-4ee0-40d0-8748-74b89ca72090.png)






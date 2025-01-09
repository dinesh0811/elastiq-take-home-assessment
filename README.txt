Note: Here I have used different locators to locate the elements.
1. I have imported all the packages required for the testing
2. Then I called webdiver with given url and also added Implicit wait for fluent process.
3. After that I have created a function to find the total entries in the table by find the length of entries per page.
4. Again I have created a for loop to find available tables to navigate using .click() method.
5. Using send_keys() method I sent the given value in the search box
6. Finally using assert I verified only given entries were listed in the table.
Note: Here I used assert function because if assert fails whole test will fail, we can easily to found the cause.

steps to run the script:
1. install latest version of python, selenium and pycharm IDE.
2. And setup pycharm and environment variable for python
3. Then start setup Python interpreter in pycharm IDE.
4. And install Pytest by clicking the add button under the interpreter.
Note: Verify all installed stuffs are available with help of commend prompt.

Once done with the Environment setup you can start the execution by entering below command in the pycharm console.
"pytest qa_selenium_test.py -v"



code:

from selenium import webdriver
from selenium.webdriver.common.by import By

driver = webdriver.Chrome()
driver.maximize_window()
driver.implicitly_wait(2)
driver.get("https://www.lambdatest.com/selenium-playground/table-sort-search-demo")

value = "New York"
total_sum = 0

def test_find_element():
    total = 0
    total_entries = driver.find_elements(By.XPATH, "//tbody/tr")
    total = len(total_entries)
    return total

total_pages = driver.find_elements(By.XPATH, "//span/a")
for j in range(len(total_pages)):
    if j == 0:
        pass
    else:
        driver.find_element(By.ID, "example_next").click()
    total_sum = total_sum + test_find_element()
assert total_sum == 24

driver.find_element(By.XPATH, "//input[@type='search']").send_keys(value)
new_sum = 0
new_sum = new_sum + test_find_element()

assert new_sum == 5
print("Verified that 5 entries listed out of 24 total entries")

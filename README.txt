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

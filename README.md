# Payroll-Management-System-using-Python

The objective for this report is to develop a Payroll Management System to generate employee information and salary. The first part of the report the flow chart of overall system. The system starts with displaying the employee menu. The system validates the user input and user then can add, view and validate employee’s record that stored in the list function. From the list function, the employee can search and view salary record. The final part is to combine every part of the section into a complete Payroll Management System.


### Table of Content
[Assumption](#Assumption)

[Design of the program – Flowcharts](#Design_of_the_program_–_Flowcharts)

[Conclusion](#Conclusion)

[Limitation](#Limitation)

[Reference](#Reference)

### Assumption

The payment management system use list and does not use the database for data storing. Hence, once the user inserts the record, the record would not be stored once the exit menu is used.

The system is designed to keep looping where the user will be given an option to return to main menu after selecting all the available options or user selects exit the program.

### Design of the program – Flowcharts

<img width="446" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/265bb740-53d0-458b-98e6-9207c650d820">

### Programing Concepts with screenshots of sample input/output and explanation

#### Part 1

The screenshot below illustrates the payroll management system's main menu. The main menu displays the system's main screen. Users are asked to select options from a menu using if, elif, and else. If the user enters 1, they will be directed to the employee's profile, 2, salary generator, 3, pay slip, and 4, exit system. If the user enters an incorrect input, the notice "Invalid input, please re-enter a valid input" appears. The function is saved as menu():.

<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/3110cb2f-dc66-4851-87cd-a2a083eea798">

The output below shows if the user enters an invalid input.

<img width="693" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/07388371-9408-4dd8-8455-c5ff1b7e4466">

#### Part 2

In this system, the list method is used to store the entry rather than the appropriate database. The employment record entered by the user is temporarily saved in the list. When the user exits the program, the employee record is removed, and the user must enter the record again.

<img width="693" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/1e14b365-c607-4fd5-bf6d-2c478433ec5c">

#### Part 2.2


Under the 1. Employee Profile option in menu, user will be given selection to choose 1. Add employee profile, 2. Update employee profile, 3. View employee profile, 4. Delete employee profile and 5. Return to main menu. Similar to main menu, if, elif, and else function is used and if the user enters an incorrect response, notice "Invalid input, please re-enter a valid input" appears. The function is named as emp_profile():.


<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/0d281a6b-36f2-4073-ad46-05b9d4d85e48">

The output below shows if the user enters an invalid input in emp_profile(): function.

<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/c773dfe1-8795-4e85-ba1f-950b79963142">


Before creating functions later on, get_positive_input(): is defined to make sure the user enter the valid value. get_positive_input(): is to guarantee that only valid non-negative integer value are accepted for all self-defined function.


<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/14e22748-7e46-45e8-925b-e6399336b77c">


Assume the employee profile is empty, the user can add the employee profile by selecting the 1st option in emp_profile(): which is 1. Add employee profile. add_employee() is a function to obtain information about a new employee and adding their profile to a global list called emp_list. The function prompt user to enter new emp_ID (employee ID), emp_name (Employee Name), and emp_dep (employee department). Once user enter the input, the user is required to enter the emp_basic (employee’s basic salary), emp_allowance (allowance), emp_bonus (bonus), and emp_overtime (overtime) if any.


<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/a9f15090-f2e3-4faf-a63e-7663097bea24">

The salary (emp_total) is calculated within calculate_salary() by adding the basic salary, allowance, bonus, and overtime. The rules are that if the employee's total income is less than RM 2000, add 5% commissions, deduct 6% tax from the employee's total salary if it is more than RM3000.


<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/ea011eb8-699d-4ac9-9497-54ec889129cd">


Once user enter the valid input, it will prompt ‘You have successfully added your employee profile!’ and the program will store the employee record into list and bring the user back to the Employee Profile menu, otherwise invalid input will prompt ‘Invalid input, please enter a valid number’.

<img width="693" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/7a1022d9-1122-43e4-8e49-c48f907d971c">

<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/44382c88-2457-4883-b748-71e52d073937">


#### 2.3

3. View employee profile, is the option to view the employee record that consist of employee’s record which is added in the list. The def display_emp will show Employee Department, Employee Total Salary, Employee Salary after EPF and Employee Salary after tax 6% or commission 5%. If, not, return function is used to check whether the employee ID entered by the user exists in the list or not. If the employee ID provided by the user is not exist in the list, the program will prompt ‘Employee ID does not exist, please proceed to add an employee profile.

<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/c97dc7a1-f9d9-4a0f-bae7-3ebfccc21244">


The output is as per below. If the employee ID exist in list, it displays employee’s information and then prompt ‘Please enter 1 to return to the main menu or 0 to exit: ‘


<img width="693" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/eacf919d-2d39-4db9-bee8-c3044a50a5a3">

<img width="693" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/19d35f7e-ffd0-4c60-b361-6087adbf1279">


#### Part 2.4

2. Salary Generator in the main menu, is the option to view the employee salary after adding basic salary, allowance, bonus, and overtime. In addition to that, the amount also includes rules if the employee’s total salary is below RM 2000, add 5% commissions, if the employee’s total salary is greater than RM3000, deduct 6% tax. Similar to def display_emp, If, not, return function is used to check whether the employee ID entered by the user exists in the list or not. If the employee ID provided by the user is not exist in the list, the program will prompt ‘Employee ID does not exist, please proceed to add an employee profile.

<img width="636" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/4eb20010-2ea9-4d48-b9c5-1a85aa3239ae">


The output is as per below. If the employee ID exist in list, it displays employee’s information and then prompt ‘Please enter 1 to return to the main menu or 0 to exit:

<img width="689" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/59e52a4b-c12d-4aa5-b399-a9532c2a7fa1">
<img width="697" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/fa9d3787-09ef-408c-a156-8daa59011ff1">


#### Part 3

The system records all the employees into list using the function below.


<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/3609456c-ef34-4219-92fa-8e3602e5c632">


In this code, the user is asked to provide information such as employee ID, name, department, base wage, allowance, bonus, and overtime. Using the calculate_salary() function, these details are then utilized to calculate total, salary. Finally, using the extend method, the employee data and calculated values are added to the global emp_list.

#### Part 3.2

Option 3, pay slip in the main menu, enable user to search their pay slip records. Similar like previous def function, def searchPayslip(): require user to enter employee ID that is already existed in list. If, not, return function is used to check whether the employee ID entered by the user exists in the list or not. If the employee ID provided by the user is not exist in the list, the program will prompt ‘Employee ID does not exist, please proceed to add an employee profile’ and bring user to Employee Profile Menu. Once the user enter an existed employee ID, user is required to choose month in the def get_month_name:. function. get_month_name takes a month number as input and returns the corresponding month name. It uses a list of month names, and the input month number is used as an index to retrieve the name.

<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/6f65ff8b-1a0b-4b8f-9031-7f1441cacf61">
<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/505e2be8-f5a6-4666-98ad-c1cc69078de8">
<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/be9fd46b-44b3-4360-bc28-dd547b74e0ba">


After the user selects a valid month (1, 2, or 3), the searchPayslip function displays a header which contains the month name from the get_month_name function.

The payslip_info function is to provide salary information, such as ID, Name, Department, Basic Salary, Allowance, Bonus, Overtime, Total Salary, Total Salary After EPF, and Total Salary After Tax or Commission. When the user enters a valid month in the searchPayslip function, the payslip_info function is called, then displays detailed pay slip information for the employee and month.

<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/0bd1eeb0-6ccf-481f-86cc-356c76f65e61">


#### Part 3.3

The output is as per below.


<img width="704" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/97e1d908-6bd0-4f01-b9e4-a9837dac9377">
<img width="700" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/c9090315-45a5-439b-8b0a-b43987c37fcd">

<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/07928a8a-4b92-4f85-a231-447e7d70fd90">

#### Part 4

By combining the part 1 to part 3, whole system can be created as per below.

#### a. addEmployee()
<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/09ec3802-368a-4ab5-aad8-d83beccc5206">
<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/923586e8-520d-4250-855b-16d8e51a1390">

#### b. generateSalary()

<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/d35da7c1-a483-4c4d-905b-de1999d22c6a">

#### c. updateEmployee()


<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/9088cdd2-dbfc-4656-a79b-262928269101">
<img width="696" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/2adddfd5-682a-4821-91d0-073d60b75334">


#### d. deleteEmployee()

This function only allowed to HR staff to do the deletion of employee data by setting password ‘hr072295’. The user is required to enter the employee ID, prompt the user if the entered employee ID does not exist.

<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/a905767c-43b2-4d66-9c55-1e233c320ff7">


#### e.searchPayslip()

<img width="697" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/c619a3da-bfec-4257-96d2-c6cb84d916a1">
<img width="692" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/478178fd-47c4-4757-96f7-9f79a318cc35">
<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/2e0c606a-7b60-45c4-be6e-999d6532939e">


#### f. viewPayslip()

Viewpayslip is divided into searchPayslip():, get_month_name():, payslip_info():. These functions iterate through the list and generate the payslip based on the selected month.

<img width="694" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/70050336-0d08-42e0-a0c2-13e8fd0f802e">
<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/13baf28f-5b26-4c15-a392-7a28dc270d51">
<img width="696" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/eafd609c-fcb1-4bb9-8cd7-495db936fc58">
<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/f85d0415-dfcd-4bce-a1ea-a11b2a295e3c">

#### g. exit()

The user is given to exit the program in the main menu.

<img width="695" alt="image" src="https://github.com/AfifRifaie95/Payroll-Management-System-using-Python/assets/159521904/452b21c7-d47c-4ada-bee2-d611844de462">


### Conclusion

The payroll administration system is used to store employee profiles, calculate salaries, and view pay slips. The program is made up of self-defined functions that perform specific tasks such as adding and editing employee profiles, calculating salaries, and displaying pay slips.

Programming elements such as functions, conditionals, loops, and error handling are employed throughout the code. The global variable emp_list temporary store information about employees in a centralized data structure that is easy to access and modify and serves as a shared data structure that keeps information about employees across functionalities in the program. The purpose of get_positive_input() is to ensure that only valid non-negative integer values are allowed for all self-defined functions in order to avoid user enters non valid input.

### Limitation

Future development could include the usage of a database for data storage. This allows the program to keep the employee data across sessions instead of one-time record.

### Reference

1. Design Flowchart In Programming (With Examples)—Programiz. (n.d.). Retrieved December 18, 2023, from https://www.programiz.com/article/flowchart-programming
2. Python list() Function. (n.d.). Retrieved December 18, 2023, from https://www.w3schools.com/python/ref_func_list.asp
3. Python, R. (n.d.-a). Python “for” Loops (Definite Iteration) – Real Python. Retrieved December 18, 2023, from https://realpython.com/python-for-loop/
4. Python, R. (n.d.-b). Using and Creating Global Variables in Your Python Functions – Real Python. Retrieved December 18, 2023, from https://realpython.com/python-use-global-variable-in-function/
5. Python User-defined Functions. (n.d.). Retrieved December 18, 2023, from https://www.programiz.com/python-programming/user-defined-function
6. Try and Except in Python—Python Tutorial. (n.d.). Retrieved December 18, 2023, from https://pythonbasics.org/try-except/

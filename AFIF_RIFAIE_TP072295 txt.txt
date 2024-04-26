#AFIF RIFA'IE BIN MOHD GAZALI
#TP072295

def menu():
    print("*********************APU PAYROLL*********************")
    print("1. Employee Profile \n2. Salary Generator \n3. Pay Slip\n4. Exit")
    choice = input("\nPlease Enter your selection: ")

    if choice == "1":
        emp_profile()
    elif choice == "2":
        salary_generator()
    elif choice == "3":
        searchPayslip()
    elif choice == "4":
        exit()
    else:
        print("Invalid input, please re-enter a valid input")
        menu()

emp_list=[]
def emp_profile():
    print("~~~~~~~~~~~~~~~~~~~\tWelcome to employee profile menu\t~~~~~~~~~~~~~~~~~~~~")
    print("1. Add employee profile")
    print("2. Update employee profile")
    print("3. View employee profile")
    print("4. Delete employee profile")
    print("5. Return to main menu")
    ch1 = input("Enter your selection: ")
    if ch1 == "1":
        add_employee()
    elif ch1 == "2":
        update_employee()
    elif ch1 == "3":
        display_emp()
    elif ch1 == "4":
        delete_emp()
    elif ch1 == "5":
        menu()
    else:
        print("Invalid input, please re-enter a valid input")
        emp_profile()

def get_positive_input(prompt):
    while True:
        try:
            value = int(input(prompt))
            if value >= 0:
                return value
            else:
                print("Please enter a non-negative value.")
        except ValueError:
            print("Invalid input, please enter a valid number.")

def add_employee():
    global emp_list  # Declare emp_list as a global variable

    emp_ID = input("Enter employee ID: ")
    emp_name = input("Enter employee name: ")
    emp_dep = input("Enter employee department: ")

    emp_basic = get_positive_input("Enter employee basic salary: ")
    emp_allowance = get_positive_input("Enter employee allowance: ")
    emp_bonus = get_positive_input("Enter employee bonus: ")
    emp_overtime = get_positive_input("Enter employee overtime: ")

    emp_total, emp_salary, emp_final = calculate_salary(emp_basic, emp_allowance, emp_bonus, emp_overtime)

    emp_list.extend(
        [emp_ID, emp_name, emp_dep, emp_basic, emp_allowance, emp_bonus, emp_overtime, emp_total, emp_salary, emp_final])

    print("You have successfully added your employee profile!")

def calculate_salary(emp_basic, emp_allowance, emp_bonus, emp_overtime):
    emp_total = emp_basic + emp_allowance + emp_bonus + emp_overtime
    emp_salary = round(emp_total - (emp_total * 11 / 100), 2)

    if 0 <= emp_salary < 2000:
        emp_final = emp_salary + (emp_salary * 5 / 100)
    elif emp_salary > 3000:
        emp_final = emp_salary - (emp_salary * 6 / 100)
    else:
        emp_final = emp_salary

    return emp_total, emp_salary, emp_final

def update_employee():
    if not emp_list:
        print("Employee ID does not exist\nPlease proceed to add an employee profile first!\n")
        emp_profile()
    else:
        employee_id_to_update = input("Enter employee ID: ")
        if employee_id_to_update == emp_list[0]:
            print("Please choose the item to update:")
            print("1. Employee Name\n2. Employee Department ")
            print("3. Employee Basic\n4. Employee Allowance\n5. Employee Bonus \n6. Employee Overtime")
            print("7. Return to employee profile")

            option = input("\nPlease enter the corresponding number to select: ")

            if option == "1":
                emp_list[1] = input("Enter new employee name: ")
            elif option == '2':
                emp_list[2] = input("Enter new employee department: ")
            elif option in {'3', '4', '5', '6'}:
                try:
                    index = int(option)
                    new_value = int(input(f"Enter new value for employee {emp_options[index]}: "))
                    assert new_value >= 0
                    emp_list[index] = new_value
                except ValueError:
                    print("Input is not a number, please try again")
                    update_employee()
                    return
                except AssertionError:
                    print("Input is a negative number, please try again")
                    update_employee()
                    return
            elif option == "7":
                emp_profile()
                return
            else:
                print("Invalid input, please try again.")
                update_employee()
                return

            print("You have successfully updated your employee profile\n")
            emp_profile()
        else:
            print("Employee ID does not exist!\nPlease try again!\n")
            emp_profile()

def display_emp():
    if not emp_list:
        print("Employee ID does not exist,\nPlease proceed to add an employee profile\n")
        emp_profile()
        return

    employee_id_to_display = input("Enter employee ID: ")

    if employee_id_to_display == emp_list[0]:
        print("Employee Name: ", emp_list[1])
        print("Employee ID: ", emp_list[0])
        print("Employee Department: ", emp_list[2])
        print("Employee Total Salary: ", emp_list[7])
        print("Employee Salary after EPF: ", emp_list[8])
        print("Employee Salary after tax or commission: ", emp_list[9])

        opt = int(input("Please enter 1 to return to the main menu or 0 to exit: "))
        if opt == 1:
            menu()
        else:
            print("Goodbye!")
    else:
        print("Employee ID does not exist!\nPlease proceed to add an employee profile first!\n")
        emp_profile()

def delete_emp():
    global hrpass

    if not emp_list:
        print("Employee ID does not exist!\nPlease proceed to add an employee profile first!\n")
        emp_profile()
        return

    password_attempt = input("Function reserved for HR department, please enter password to proceed: ")

    if password_attempt == hrpass:
        emp_list.clear()
        print("Password verified, employee records successfully deleted.")
        menu()  # Return to the main menu after successful deletion
    else:
        print("Password incorrect, function reserved for HR department.")
        emp_profile()

hrpass = "hr072295"

def salary_generator():
    if not emp_list:
        print("Employee ID does not exist!\nPlease proceed to add an employee profile first!\n")
        menu()
        return

    employee_id_to_generate_salary = input("Enter employee ID: ")

    if employee_id_to_generate_salary == emp_list[0]:
        emp_total = int(emp_list[3]) + int(emp_list[4]) + int(emp_list[5]) + int(emp_list[6])
        emp_salary = round(emp_total - (emp_total * 11 / 100), 2)
        print(f"The salary for employee ID {emp_list[0]} is: ${emp_salary:.2f}")

        opt = int(input("Please enter 1 to return to the main menu or 0 to exit: "))
        if opt == 1:
            menu()
        else:
            print("Goodbye!")
    else:
        print("Employee ID does not exist!\nPlease proceed to add an employee profile first!\n")
        menu()

def searchPayslip():
    if not emp_list:
        print("Employee ID does not exist!\nPlease proceed to add an employee profile first!\n")
        emp_profile()
        return

    employee_id_to_search_payslip = input("Enter employee ID: ")

    if employee_id_to_search_payslip == emp_list[0]:
        print("Select the month to view the payslip:")
        print("1. January 2023\n2. February 2023\n3. March 2023")

        month_selection = input("Enter the corresponding number to select the month: ")

        if month_selection in {"1", "2", "3"}:
            print(f"===================={get_month_name(month_selection)} Payslip====================")
            payslip_info()
        else:
            print("Invalid input, please try again.")
            searchPayslip()

        opt = int(input("Please enter 1 to return to the main menu or 0 to exit: "))
        if opt == 1:
            menu()
        else:
            print("Goodbye!")
    else:
        print("Employee ID does not exist,\nPlease proceed to add an employee profile.\n")
        emp_profile()

def get_month_name(month_number):
    months = ["", "January", "February", "March"]
    return months[int(month_number)]

def payslip_info():
    print("ID | Name | Department")
    print(emp_list[0], "|", emp_list[1], "|", emp_list[2])
    print("Basic Salary: ", emp_list[3])
    print("Allowance: ", emp_list[4])
    print("Bonus: ", emp_list[5])
    print("Overtime: ", emp_list[6])
    print("Total Salary: ", emp_list[7])
    print("Total Salary After EPF: ", emp_list[8])
    print("Total Salary After Tax or Commission: ", emp_list[9])
    print("========================================================================================")

def menu():
    print("~~~~~~~~~~~~~~~~~~~\tAPU PAYROLL\t~~~~~~~~~~~~~~~~~~~~")
    print("1. Employee Profile \n2. Salary Generator \n3. Pay Slip\n4. Exit")
    choice = input("\nPlease Enter your selection: ")

    if choice == "1":
        emp_profile()
    elif choice == "2":
        salary_generator()
    elif choice == "3":
        searchPayslip()
    elif choice == "4":
        exit()
    else:
        print("Invalid input, please re-enter a valid input")
        menu()
menu()
emp_profile()
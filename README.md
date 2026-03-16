class ATM:

    def __init__(self):
        self.pin = ""
        self.balance = 0
        self.menu()
    account = {
        "sangu": 50000,
        "shivu": 30000,
        "vinay": 10000
    }


    def menu(self):
        while True:
            print("""
            press
            1 for create pin
            2 for change pin
            3 for check balance
            4 for withdraw
            5 for exit
            """)

            user_input = input("Enter your choice: ")

            if user_input == "1":
                self.create_pin()

            elif user_input == "2":
                self.change_pin()

            elif user_input == "3":
                self.check_balance()

            elif user_input == "4":
                self.withdraw()

            elif user_input == "5":
                print("Thank you for using ATM")
                break

            else:
                print("Invalid Choice")

    def create_pin(self):
        if self.pin != "":
            print("Pin already created")
            return

        print("Create Pin")
        self.pin = input("Enter new pin: ")
        self.balance = int(input("Enter initial balance: "))
        print("Pin created successfully")


    def check_balance(self):
        if self.pin == "":
            print("First create pin")
            return

        user_pin = input("Enter pin: ")
        if user_pin == self.pin:
            print("Your Balance is:", self.balance)
        else:
            print("Wrong Pin")

    def withdraw(self):
        if self.pin == "":
            print("First create pin")
            return

        user_pin = input("Enter pin: ")
        if user_pin == self.pin:
            amount = int(input("Enter amount: "))
            if amount <= self.balance:
                self.balance -= amount
                print("Withdraw successful")
                print("Remaining Balance:", self.balance)
            else:
                print("Insufficient Balance")
        else:
            print("Wrong Pin")

    def deposit(self):
        if self.pin == "":
            print("First create pin")
            return
        
        user_pin = input("Enter pin: ")
        if user_pin == self.pin:
            amount = int(input("Enter amount: "))
            self.balance += amount
            print("Deposit successful =", self.balance)
        else:
            print("Wrong Pin")\
    
 
    def change_pin(self):
        if self.pin == "":
            print("First create pin")
            return

        old_pin = input("Enter old pin: ")
        if old_pin == self.pin:
            self.pin = input("Enter new pin: ")
            print("Pin changed successfully")
        else:
            print("Wrong Pin")   
      


sbi = ATM()


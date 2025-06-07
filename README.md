# ATM-oops-python-
class ATM :
    def __init__(self):
        print(id(self))
        self.pin=""
        self.balance = 0
        self.menu()
    def menu(self):
        user_input = input("""
        hi how can i help you ?
        1.press 1 to create pin.
        2.press 2 to change pin.
        3.press 3 to check balance.
        4.press 4 to check withdraw.
        5.Exit
        """)
        if user_input == "1" :
            self.create_pin()
        elif user_input == "2":
            self.change_pin()
        elif user_input == "3":
            self.check_balance()
        elif user_input == "4":
            self.withdraw()
        else :
            exit()
    def create_pin(self):
        user_pin = input("enter your pin: ")
        self.pin = user_pin
        user_balance = int(input("enter your balance: "))
        self.balance = user_balance
        print("pin create sucessfully")
        self.menu()
    def change_pin(self):
        old_pin = input("enter your old pin: ")
        if old_pin == self.pin:
            new_pin = input("enter your new pin: ")
            self.pin = new_pin
            print('pin change successful')
            self.menu()
        else:
            print("try again")
            self.menu()
    def check_balance(self):
        user_pin = input("enter your pin: ")
        if user_pin == self.pin:
            print('your balance is ',self.balance)
        else:
            print('no balance')
        self.menu()
    def withdraw(self):
        user_pin = input("enter the pin: ")
        if user_pin == self.pin:
            amount = int(input("enter the amount: "))
            if amount <= self.balance:
                self.balance = self.balance - amount
                print("withdrawl successful.balance is",self.balance)
            else:
                print("no balance")
        else:
            print("try again")
        self.menu()

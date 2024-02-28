from datetime import datetime
import pytz
datetime_in_ph = datetime.now(pytz.timezone("Asia/Manila"))
formated_date_time = datetime_in_ph.strftime("%B %d, %Y , %I:%M:%S %p")
print(formated_date_time)
import random

class BankAccount:

    def __init__(self, balance=0,accountID = ""):
        self.balance = balance
        self.accountID = accountID
        
    def deposit(self, amount=0):
        self.balance = self.balance + amount
        print("You successfully deposit $", amount, "your current balance is $", str(self.balance))

    def withdraw(self, amount=0):
        if self.balance >= amount:
            self.balance = self.balance - amount
            print("You successfully withdraw", str(amount), "your current balance is", str(self.balance))
        else:
            print(f"You don't have sufficient amount to withdraw your current balance is {self.balance}")

    def get_balance(self):
        print("Your current balance is", self.balance)

    def display_info(self,accoundID):
        print(f"Good day your accountID is {accoundID} and your current balance is {self.balance}")


database = {
    # ID : BALANCE
}
while True:
    login_or_signup = input("Log in or Sign up: ").lower()
    if login_or_signup == "login" or login_or_signup == "log in":
        user_accountID = input("Enter accountID: ")
        if user_accountID in database:
            deposit_or_withdraw = input(
                f"Good day {user_accountID}, What's your transaction?\n (1) Deposit\n (2) Withdraw\n (3) Check my Balance\n (4) Check my information: ")
            if deposit_or_withdraw == "1":
                while True:
                    try:
                        amount = int(input("Enter the amount you want to deposit: "))
                        database[user_accountID].deposit(amount)
                        break
                    except:
                        print("Invalid input. Please only enter a valid amount.")

            elif deposit_or_withdraw == "2":
                while True:
                    try:
                        amount = int(input("Enter the amount you want to withdraw: "))
                        database[user_accountID].withdraw(amount)
                        break
                    except:
                        print("Invalid input. Please only enter a valid amount.")
                        break

            elif deposit_or_withdraw == "3":
                database[user_accountID].get_balance()

            elif deposit_or_withdraw == "4":
                database[user_accountID].display_info(user_accountID)

            else:
                print("Invalid")
                break
        else:
            print("You don't have an account yet")

    elif login_or_signup == "signup" or login_or_signup == "sign up":
        accountname = input("Enter your name: ")
        accountnumber = random.randint(0, 9999)
        created_accountID = str(accountname) + str(accountnumber)
        print(f"Congratulations your accountID '{created_accountID}' is created")
        database.update({created_accountID: int(0)})

        database[created_accountID] = BankAccount(balance=0)

    else:
        print("Invalid input")






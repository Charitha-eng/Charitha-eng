

class BankAccount:
    # Interest rate for all accounts
    interest_rate = 3.5

    def __init__(self, account_holder, balance):
        self.account_holder = account_holder
        self.balance = balance

    def deposit(self, amount):
        if amount > 0:
            self.balance += amount
            print(f"Deposited {amount:.2f}. New balance is {self.balance:.2f}.")
        else:
            print("Amount must be greater than zero.")

    def withdraw(self, amount):
        if amount > 0:
            if self.balance >= amount:
                self.balance -= amount
                print(f"Withdrew {amount:.2f}. New balance is {self.balance:.2f}.")
            else:
                print("Not enough balance.")
        else:
            print("Amount must be greater than zero.")

    def display_balance(self):
        print(f"Account Holder: {self.account_holder}, Balance: {self.balance:.2f}")

# Running the code
if __name__ == "__main__":
    # Create a bank account
    account = BankAccount("Your Name", 1000.0)

    # Show the initial balance
    account.display_balance()

    # Deposit money
    account.deposit(500.0)

    # Withdraw money
    account.withdraw(200.0)

    # Try withdrawing more money than available
    account.withdraw(1500.0)

    # Show the final balance
    account.display_balance()



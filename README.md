# calculator
This Python program is a basic calculator that performs addition, subtraction, multiplication, and division. It uses functions for each operation and prompts the user to choose an option and enter two numbers. It then displays the result, with error handling for division by zero to ensure safe operation.


def add(x, y):
    return x + y

def subtract(x, y):
    return x - y

def multiply(x, y):
    return x * y

def divide(x, y):
    if y == 0:
        return "Cannot divide by zero"
    return x / y

print("Simple Calculator")
print("Choose what you want to do:")
print("1 - Add")
print("2 - Subtract")
print("3 - Multiply")
print("4 - Divide")

while True:
    choice = input("Pick an option (1/2/3/4): ")

    if choice not in ['1', '2', '3', '4']:
        print("That wasn't a valid option. Try again.")
        continue

    try:
        num1 = float(input("Enter your first number: "))
        num2 = float(input("Enter your second number: "))
    except ValueError:
        print("Numbers only please!")
        continue

    if choice == '1':
        result = add(num1, num2)
        print(f"{num1} + {num2} = {result}")
    elif choice == '2':
        result = subtract(num1, num2)
        print(f"{num1} - {num2} = {result}")
    elif choice == '3':
        result = multiply(num1, num2)
        print(f"{num1} * {num2} = {result}")
    elif choice == '4':
        result = divide(num1, num2)
        print(f"{num1} / {num2} = {result}")

    again = input("Do you want to calculate something else? (yes/no): ").strip().lower()
    if again != 'yes':
        print("Alright, thanks for using the calculator!")
        break

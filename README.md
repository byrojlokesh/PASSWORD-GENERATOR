# PASSWORD-GENERATOR
The Password Generator is a Python command-line tool that lets users create secure and customizable passwords. It gives users control over the length of the password and the types of characters used, including uppercase letters, lowercase letters, digits, and special characters.

This project demonstrates core programming skills in Python such as:
1. User input handling
2. String manipulation
3. Random selection
4. Functional programming (use of functions)
5. Loop and conditional logic
-------------------------------------------------------------------------------------------
code to generate Random Password:

import random
import string

def gen_psw(length,uppercase,lowercase,digits,specials):
    charac = ""
    if uppercase:
        charac += string.ascii_uppercase
    if lowercase:
        charac += string.ascii_lowercase
    if digits:
        charac+= string.digits
    if specials:
        charac += string.punctuation

    if not charac:
        return "Error: No character set selected!"

    password = ''.join(random.choice(charac) for _ in range(length))
    return password

def main():
    print("GENERATE YOUR PASSWORD")

    while True:
        try:
            length = int(input("Enter password length: "))
        except ValueError:
            print("Please enter a valid number.")
            continue

        uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
        lowercase = input("Include lowercase letters? (y/n): ").lower() == 'y'
        digits = input("Include numbers? (y/n): ").lower() == 'y'
        specials = input("Include special characters? (y/n): ").lower() == 'y'

        psw = gen_psw(length,uppercase,lowercase,digits,specials)
        print("\nGenerated Password:", psw)

        again = input("\nDo You Wish To Generate Another Password? (y/n): ").lower()
        if again != 'y':
            print("Ok then Bye!")
            break

if __name__ == "__main__":
    main()
--------------------------------------------------------------------------------------
output for the code:

GENERATE YOUR PASSWORD
Enter password length: 12
Include uppercase letters? (y/n): y
Include lowercase letters? (y/n): y
Include numbers? (y/n): y
Include special characters? (y/n): y

Generated Password: T4v@k^5Mz0qP

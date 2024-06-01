# Nandinisettipalli_PasswordGenerator.py
import random
import string

def generate_password(length):
    if length < 4:
        raise ValueError("Password length should be at least 4 characters")
    
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for i in range(length))
    
    return password

def main():
    print("Welcome to the Password Generator!")
    
    try:
        length = int(input("Enter the desired password length: "))
        count = int(input("Enter the number of passwords to generate: "))
        
        if length < 4:
            print("Password length should be at least 4 characters.")
            return
        
        for _ in range(count):
            print(generate_password(length))
    
    except ValueError:
        print("Please enter a valid number.")
        
if __name__ == "__main__":
    main()

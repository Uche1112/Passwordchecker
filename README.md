import string
import getpass

def check_pwd():
    password = getpass.getpass("Enter Your password: ")
    strength = 0
    remarks = ""
    lower_count = upper_count = num_count = special_count = 0

    for char in password:
        if char in string.ascii_lowercase:
            lower_count += 1
        elif char in string.ascii_uppercase:
            upper_count += 1
        elif char in string.digits:
            num_count += 1
        else:
            special_count += 1

    if lower_count >= 1:
        strength += 1
    if upper_count >= 1:
        strength += 1
    if num_count >= 1:
        strength += 1
    if special_count >= 1:
        strength += 1

    if strength == 1:
        remarks = "Bad Password! Please Change"
    elif strength == 2:
        remarks = "Not A Good Password! Please Change"
    elif strength == 3:
        remarks = "Weak password, consider changing"
    elif strength == 4:
        remarks = "Hard password, kindly Improve"
    elif strength == 5:
        remarks = "A very strong password"

    print("Your password has:")
    print(f"{lower_count} lowercase characters")
    print(f"{upper_count} uppercase characters")
    print(f"{num_count} numeric characters")
    print(f"{special_count} special characters")

    print(f"Password Strength: {strength}")
    print(f"Hint: {remarks}")

if __name__ == "__main__":
    print("WELCOME TO UCHE PASSWORD STRENGTH CHECKER")
    check_pwd()

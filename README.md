# Password-complexity-checker
import re

def assess_password_strength(password):
    strength = 0
    feedback = ""
    if len(password) < 8:
        feedback += "Password is too short. "
    else:
        strength += 1
    # Check for uppercase letters
    if re.search(r"[A-Z]", password):
        strength += 1
    else:
        feedback += "Password should contain at least one uppercase letter. "
    # Check for lowercase letters
    if re.search(r"[a-z]", password):
        strength += 1
    else:
        feedback += "Password should contain at least one lowercase letter. "
    # Check for numbers
    if re.search(r"\d", password):
        strength += 1
    else:
        feedback += "Password should contain at least one number. "
    # Check for special characters
    if re.search(r"[!@#$%^&*()_+=-{};:'<>,./?]", password):
        strength += 1
    else:
        feedback += "Password should contain at least one special character. "
    # Calculate password strength
    if strength == 5:
        password_strength = "Strong"
    elif strength >= 3:
        password_strength = "Medium"
    else:
        password_strength = "Weak"
    return password_strength, feedback

def main():
    password = input("Enter a password: ")
    password_strength, feedback = assess_password_strength(password)
    print(f"Password strength: {password_strength}")
    print(feedback)

if name == "main":
    main()

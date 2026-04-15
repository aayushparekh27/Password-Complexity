import re

def check_password_strength(password):
    strength = 0
    feedback = []

    # Criteria checks
    if len(password) >= 8:
        strength += 1
    else:
        feedback.append("Password should be at least 8 characters long.")

    if re.search(r"[A-Z]", password):
        strength += 1
    else:
        feedback.append("Add at least one uppercase letter.")

    if re.search(r"[a-z]", password):
        strength += 1
    else:
        feedback.append("Add at least one lowercase letter.")

    if re.search(r"\d", password):
        strength += 1
    else:
        feedback.append("Add at least one number.")

    if re.search(r"[!@#$%^&*()_+\-=\[\]{};':\"\\|,.<>\/?]", password):
        strength += 1
    else:
        feedback.append("Add at least one special character (!@#$, etc).")

    # Final rating
    if strength <= 2:
        rating = "Weak"
    elif strength == 3 or strength == 4:
        rating = "Moderate"
    else:
        rating = "Strong"

    return rating, feedback


def main():
    print("=== Password Strength Checker ===")
    password = input("Enter your password: ")
    rating, suggestions = check_password_strength(password)

    print("\nPassword Strength:", rating)
    if suggestions:
        print("Suggestions to improve:")
        for tip in suggestions:
            print(" -", tip)
    else:
        print("Great! Your password is strong.")

if __name__ == "__main__":
    main()

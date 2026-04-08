import random
import string

def strong_password(length):
    if length < 4:
        return "Password length should be at least 4"

    upper = random.choice(string.ascii_uppercase)
    lower = random.choice(string.ascii_lowercase)
    digit = random.choice(string.digits)
    special = random.choice(string.punctuation)

    remaining = ''.join(random.choice(string.ascii_letters + string.digits + string.punctuation) for _ in range(length - 4))

    password = upper + lower + digit + special + remaining
    password = ''.join(random.sample(password, len(password)))  # shuffle

    return password

length = int(input("Enter password length: "))
print("Strong Password:", strong_password(length))

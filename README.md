# Hello-Git
#This is my first git repo

#Help me build something new using different minds across world.
import random
import string

print("--- Robust Password Generator ---")

# 1. Get user input for password configuration
length = int(input("Enter desired password length: "))
include_uppercase = input("Include uppercase letters? (y/n): ").lower() == 'y'
include_numbers = input("Include numbers? (y/n): ").lower() == 'y'
include_special = input("Include special characters? (y/n): ").lower() == 'y'

# 2. Build the pool of available characters based on rules
character_pool = string.ascii_lowercase  # Always start with lowercase
if include_uppercase:
    character_pool += string.ascii_uppercase
if include_numbers:
    character_pool += string.digits
if include_special:
    character_pool += string.punctuation

# 3. Generate the password securely
if len(character_pool) == 0:
    print("Error: You must allow at least one character type.")
else:
    password = []
    for i in range(length):
        random_char = random.choice(character_pool)
        password.append(random_char)
    
    # Convert list of characters back into a solid string
    final_password = "".join(password)
    print(f"\nGenerated Password: {final_password}")

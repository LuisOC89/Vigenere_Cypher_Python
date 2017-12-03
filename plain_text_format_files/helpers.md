**THIS is the source code for the program helpers.py**
===
---

```
def rotate_character(char, rot):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    #For numbers higher than 26 (26 total values in alphabet)
    fixed_rot = rot % 26 
    #For non-alphabetical characters
    if char.lower() not in alphabet: 
        letter_after_rotating_position = char
        return letter_after_rotating_position
    #For alphabetical characters
    elif char.lower() in alphabet:
        #For lower case   
        if char == char.lower():
            current_position = alphabet.find(char)
            after_rotating_position = (current_position + fixed_rot) % 26
            letter_after_rotating_position = alphabet[after_rotating_position]
            return letter_after_rotating_position    
        #For upper case
        elif char != char.lower():
            current_position = alphabet.find(char.lower())
            after_rotating_position = (current_position + fixed_rot) % 26
            letter_after_rotating_position = alphabet[after_rotating_position].upper()
            return letter_after_rotating_position
```

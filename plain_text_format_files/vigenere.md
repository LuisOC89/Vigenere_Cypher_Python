**THIS is the source code for the program decypher_vigenere.py**
===
---

```
from helpers import rotate_character

def encrypt(text, akey):
    alphabet = "abcdefghijklmnopqrstuvwxyz"
    string_text_key = creating_string_with_keyword(text, akey)

    encrypted = ""
    for index_value in range(len(text)):
        each_char = text[index_value]
        if each_char == " ":
            encrypted = encrypted + " "
        elif each_char.isalpha() == False:
            encrypted = encrypted + each_char
        else:
            encrypted = encrypted + rotate_character(each_char, alphabet.find(string_text_key[index_value]))       
    return encrypted

def creating_string_with_keyword(original_text, akey):
    str_key = ""
    space_counter = 0
    for counter in range(len(original_text)):
        each_char = original_text[counter]
        if each_char == " ":
            str_key = str_key + " "
            space_counter = space_counter + 1
        elif each_char.isalpha() == False:
            str_key = str_key + ' '
            space_counter = space_counter + 1 
        else:
            str_key = str_key + akey[(counter - space_counter) % len(akey)]     
    return str_key

def main():
    '''print("Meet me at the park at eleven am")
    print(creating_string_with_keyword("Meet me at the park at eleven am", 'bacon'))
    print(encrypt_vigenere("Meet me at the park at eleven am", 'bacon'))'''

    user_text = input("Type a message: \n")
    user_rotation = input("Encryption key: \n")
    print(encrypt(user_text, user_rotation))

if __name__ == "__main__":
    main()
```    

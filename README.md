# Prodigy-CySec-CaesarCypher
to perform encryption and decryption

def encrypt(text, shift):
    result = ""
    for char in text:
        if char.isalpha():
            shift_base = 65 if char.isupper() else 97
            result += chr((ord(char) - shift_base + shift) % 26 + shift_base)
        else:
            result += char
    return result

def decrypt(text, shift):
    return encrypt(text, -shift)

def main():
    choice = input("Would you like to (E)ncrypt or (D)ecrypt? ").upper()
    message = input("Enter your message: ")
    shift = int(input("Enter shift value: "))

    if choice == 'E':
        print("Encrypted message:", encrypt(message, shift))
    elif choice == 'D':
        print("Decrypted message:", decrypt(message, shift))
    else:
        print("Invalid choice. Please enter 'E' or 'D'.")

if __name__ == "__main__":
    main()


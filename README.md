import string

def encrypt(text, shift):
    alphabet = string.ascii_lowercase
    shifted_alphabet = alphabet[shift:] + alphabet[:shift]
    table = str.maketrans(alphabet + alphabet.upper(), shifted_alphabet + shifted_alphabet.upper())
    return text.translate(table)

def decrypt(text, shift):
    return encrypt(text, -shift)

message = input("Enter the message: ")
shift_value = int(input("Enter the shift value: "))

encrypted_message = encrypt(message, shift_value)
print(f"Encrypted Message: {encrypted_message}")

decrypted_message = decrypt(encrypted_message, shift_value)
print(f"Decrypted Message: {decrypted_message}")

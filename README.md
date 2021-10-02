from cryptography.fernet import Fernet

file = open('key.txt', 'rb')
key = file.read()
file.close()

with open('textsecured.txt', 'rb') as f:
    data = f.read()

fernet = Fernet(key)
decrypted = fernet.decrypt(data)

with open('textawal.txt', 'wb') as f:
    f.write(decrypted)

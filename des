from Crypto.Cipher import DES
from Crypto.Random import get_random_bytes
from Crypto.Util.Padding import pad, unpad

def generate_random_key():
    return get_random_bytes(8)  # 8 bytes (64 bits) for DES key

def encrypt_data(key, data):
    cipher = DES.new(key, DES.MODE_ECB)
    padded_data = pad(data.encode('utf-8'), DES.block_size)
    encrypted_data = cipher.encrypt(padded_data)
    return encrypted_data

def decrypt_data(key, encrypted_data):
    cipher = DES.new(key, DES.MODE_ECB)
    decrypted_data = cipher.decrypt(encrypted_data)
    return unpad(decrypted_data, DES.block_size).decode('utf-8')

if __name__ == "__main__":
    # Example usage
    key = generate_random_key()
    plaintext = "This is a secret message."

    encrypted_data = encrypt_data(key, plaintext)
    print(f"Encrypted data: {encrypted_data.hex()}")

    decrypted_data = decrypt_data(key, encrypted_data)
    print(f"Decrypted data: {decrypted_data}")

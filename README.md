# dynamic-url-encryption
PHP function for dynamic URL encryption and decryption using AES, SHA3, and Base64.
This library helps protect your web application from SQL Injection attacks by obfuscating URL parameters in a secure, irreversible way.

<br>
<br>

## 📁 Features

🔒 AES-256-CBC encryption

🛡️ HMAC-based integrity verification (SHA3-256)

🌐 URL-safe Base64 encoding

⚡ Lightweight functional approach (no classes or dependencies)

✅ Easy to integrate into existing PHP projects

<br>
<br>

## 🔑 Configuration
Make sure to define a constant SECRET_KEY before using the functions:

```define('SECRET_KEY', 'your-32-byte-secret-key-goes-here');```
<br>
<br>
The secret key must be exactly 32 bytes for AES-256-CBC. You can use a key generator or hash a passphrase with SHA-256 to ensure proper length.

<br>
<br>

## 💡 How It Works
- A random 16-byte IV is generated for each encryption.
- Data is encrypted using AES-256-CBC.
- A HMAC (sha3-256) is computed for integrity protection.
- The result (IV + ciphertext + HMAC) is encoded with URL-safe Base64.

On decryption:
- The HMAC is verified before decryption
- Data is returned only if integrity and decryption succeed

<br>
<br>

## 👨‍💻 Author
Created by [@alvar27](https://github.com/alvar27)
<br>
Feel free to fork, improve, or contribute. Happy coding!

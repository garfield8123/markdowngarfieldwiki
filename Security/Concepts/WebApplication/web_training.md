# Web Application Training (Port Swinger)

![Web application database diagram](../../../images/webapplicationdatabasediagram.png)

## Web application common attacks

* Log in at the website: The attacker can try to discover the password by trying many words. The attacker would use a long list of passwords with an automated tool to test them against the login page.
* Search for the product: The attacker can attempt to breach the system by adding specific characters and codes to the search term. The attacker’s objective is for the target system to return data it should not or execute a program it should not.
* Provide payment details: The attacker would check if the payment details are sent in cleartext or using weak encryption. Encryption refers to making the data unreadable without knowing the secret key or password.

## Identification and Authentication Failure

Identification refers to the ability to identify a user uniquely. In contrast, authentication refers to the ability to prove that the user is whom they claim to be. The online shop must confirm the user’s identity and authenticate them before they can use the system

* Allowing the attacker to use brute force, i.e., try many passwords, usually using automated tools, to find valid login credentials.
* Allowing the user to choose a weak password. A weak password is usually easy to guess.
* Storing the users’ passwords in plain text. If the attacker manages to read the file containing the passwords, we don’t want them to be able to learn the stored password.

## Broken Access Control

Insecure Direct Object References (IDOR)

Access control ensures that each user can only access files (documents, images, etc.) related to their role or work.

* Failing to apply the principle of the least privilege and giving users more access permissions than they need. For example, an online customer should be able to view the prices of the items, but they should not be able to change them.
* Being able to view or modify someone else’s account by using its unique identifier. For example, you don’t want one bank client to be able to view the transactions of another client.
* Being able to browse pages that require authentication (logging in) as an unauthenticated user. For example, we cannot let anyone view the webmail before logging in.

## Injection

An injection attack refers to a vulnerability in the web application where the user can insert malicious code as part of their input. One cause of this vulnerability is the lack of proper validation and sanitization of the user’s input.

## Cryptographic Failures

Cryptography focuses on the processes of encryption and decryption of data. Encryption scrambles cleartext into ciphertext, which should be gibberish to anyone who does not have the secret key to decrypt it. In other words, encryption ensures that no one can read the data without knowing the secret key. Decryption converts the ciphertext back into the original cleartext using the secret key.

* Sending sensitive data in clear text, for example, using HTTP instead of HTTPS. HTTP is the protocol used to access the web, while HTTPS is the secure version of HTTP. Others can read everything you send over HTTP, but not HTTPS.
* Relying on a weak cryptographic algorithm. One old cryptographic algorithm is to shift each letter by one. For instance, “TRY HACK ME” becomes “USZ IBDL NF.” This cryptographic algorithm is trivial to break.
* Using default or weak keys for cryptographic functions. It won’t be challenging to break the encryption that used 1234 as the secret key.
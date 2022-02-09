# Notification
We used Telegram because it is more secure than mass market messengers like Whatsapp and Line. Telegram is based on the **MTProto protocol** which is built upon time-tested algorithms to make security compatible with high-speed delivery and reliability on weak connections. This is useful in our project as it allows for the 2FA to perform without hitch so long as the system is turned on.

# Encryption
## How is data encrypted?
Telegram supports **two layers of secure encryption** where the Server-Client Encryption is used in Cloud Chats. Telegram's encryption is based on 256-bit symmetric AES encryption, 2048-bit RSA Encryption, and Diffe-Hellman secure key exchange.

## What is MTProto protocol?
It is a protocol is designed for access to a server API from applications running on **mobile devices**.

The protoccol is subdivided into three virtually independent components:
- **High-level component (API query language):** defines the method whereby API queries and responses are converted to binary messages.
- **Cryptographic (authorization) layer:** defines the method by which messages are encrypted prior to being transmitted through the transport protocol.
- **Transport component:** defines the method for the client and the server to transmit messages over some other existing network protocol (such as HTTP, HTTPS, WS (plain websockets), WSS (websockets over HTTPS), TCP, UDP).

![Flow Diagram](https://core.telegram.org/file/811140746/2/CzMyJPVnPo8.81605/c2310d6ede1a5e220f)

## Message Encryption in MTProto
Each plaintext message encrypted in MTProto always contains the following data to be checked upon decryption in order to make the system robust against known problems with the components:
- server salt (64-Bit)
- session id
- message sequence number
- message length
- time

# Authentication
## How are MTProto messages authenticated?
Telegram ensures that msg_key is equal to SHA-256 of a fragment of the auth_key concatenated with the decrypted message (including 12…1024 bytes of random padding). The plaintext also always contains message length, server salt, session_id and other data not known to the attacker. AES decryption keys depend both on msg_key, and on auth_key, known only to the parties involved in the exchange.

## How is the server authenticated during DH key exchange?
The DH exchange is authenticated with the server's public RSA-key that is built into the client (the same RSA-key is also used for protection against MitM attacks).

## How are clients authenticated?
Various secrets (nonce, server_nonce, new_nonce) exchanged during key generation guarantee that the DH-key can only be obtained by the instance that initiated the exchange. Notice that new_nonce is transferred explicitly only once, inside an RSA-encrypted message from the client to the server.

# Protection against known attacks
## Known-Plaintext Attacks
Known-plaintext attack (KPA) is an attack model for cryptanalysis where the attacker has samples of both the plaintext, and its encrypted version (ciphertext). AES IGE that is used in MTProto is robust against KPA attacks. On top of that, the plaintext in MTProto always contains server_salt and session id.

## Chosen-Plaintext Attacks
Chosen-plaintext attack (CPA) is an attack model for cryptanalysis which presumes that the attacker has the capability to choose arbitrary plaintexts to be encrypted and obtain the corresponding ciphertexts. MTProto uses AES in IGE mode that is secure against non-adaptive CPAs. IGE is known to be not secure against blockwise-adaptive CPA, but MTProto fixes this in the following manner:

Each plaintext message to be encrypted always contains the following to be checked upon decryption:
- server salt (64-Bit)
- message sequence number
- time

On top of this, in order to replace the plaintext, you would also need to use the right AES key and iv, both dependent on the auth_key. This makes MTProto robust against a CPA.

## Man-in-the-middle attacks
Client-Server communication is protected from MiTM-attacks during DH key generation by means of a server RSA public key embedded into client software.  Visualizations of the key are presented in the form of [identicons](https://telegram.org/img/key_image.jpg). By comparing key visualizations users can make sure no MITM attack had taken place. 

## Hash collisions for Diffie-Hellman Keys
Currently, the fingerprint uses 128-bits of SHA-1 concatenated with 160 bits from the SHA-256 of the key, yielding a total of 288 fingerprint bits, thus negating the possibility of hash-collision attacks.

https://telegram.org/faq#q-how-secure-is-telegram
https://telegram.org/faq#q-so-how-do-you-encrypt-data
https://core.telegram.org/techfaq

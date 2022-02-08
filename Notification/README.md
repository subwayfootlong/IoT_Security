# Notification
We used Telegram because it is more secure than mass market messengers like Whatsapp and Line. Telegram is based on the **MTProto protocol** which is built upon time-tested algorithms to make security compatible with high-speed delivery and reliability on weak connections. This is useful in our project as it allows for the 2FA to perform without hitch so long as the system is turned on.

## How is data encrypted?
Telegram supports **two layers of secure encryption** where the Server-Client Encryption is used in Cloud Chats. Telegram's encryption is based on 256-bit symmetric AES encryption, 2048-bit RSA Encryption, and Diffe-Hellman secure key exchange.

## What is MTProto protocol?
It is a protocol is designed for access to a server API from applications running on **mobile devices**.

The protoccol is subdivided into three virtually independent components:
- **High-level component (API query language):** defines the method whereby API queries and responses are converted to binary messages.
- **Cryptographic (authorization) layer:** defines the method by which messages are encrypted prior to being transmitted through the transport protocol.
- **Transport component:** defines the method for the client and the server to transmit messages over some other existing network protocol (such as HTTP, HTTPS, WS (plain websockets), WSS (websockets over HTTPS), TCP, UDP).

![Flow Diagram](https://core.telegram.org/file/811140746/2/CzMyJPVnPo8.81605/c2310d6ede1a5e220f)

https://telegram.org/faq#q-how-secure-is-telegram
https://telegram.org/faq#q-so-how-do-you-encrypt-data
https://core.telegram.org/techfaq

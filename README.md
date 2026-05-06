# Distributed Systems — Messaging Service

**Universidad Carlos III de Madrid · 2025-2026**

We want to create a simplified messaging service between users connected over the Internet, similar to WhatsApp but with reduced functionality. Developed as part of our Distributed Systems course.

---

## Project Structure

```
.
├── Makefile
├── README.md
├── requirements.txt
└── src/
    ├── client/
    │   └── client.py       # Python client
    └── server/
        └── server.c        # C server
```

---

## Description

The system allows users to register, connect, and exchange text messages through a central messaging server. Messages sent to offline users are queued and delivered when they reconnect.

The server is written in **C** and the client in **Python**. Communication is handled via **TCP sockets**.

---

## Usage

### Server

```bash
./server -p <port>
```

### Client

```bash
python3 src/client/client.py -s <server_ip> -p <port>
```

---

## Available Commands
| Command                                  | Description                           |
|------------------------------------------|---------------------------------------|
| `REGISTER <username>`                    | Register a new user                   |
| `UNREGISTER <username>`                  | Remove a user from the system         |
| `CONNECT <username>`                     | Connect to the service                |
| `DISCONNECT <username>`                  | Disconnect from the service           |
| `USERS`                                  | List all currently connected users    |
| `SEND <username> <message>`              | Send a text message to a user         |
| `SENDATTACH <username> <file> <message>` | Send a message with a file attachment |
| `QUIT`                                   | Exit the client                       |
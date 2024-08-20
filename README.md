# Simple-Chat-Application

This project is a simple chat application that demonstrates basic socket programming and inter-process communication using forked processes to handle multiple clients. The server is designed to run on a CentOS system, while clients run on Fedora.

## Features
- Basic client-server architecture using TCP sockets.
- Server can handle multiple clients simultaneously.
- Simple username and password registration.
- Communication between two clients, with server relaying messages.
- Graceful handling of chat termination.

## Prerequisites

- **CentOS** for running the server.
- **Fedora** for running the clients.
- Basic understanding of C programming and socket programming.

## Getting Started

### 1. Clone the Repository
```bash
git clone https://github.com/IT21826740/simple-chat-application.git
cd simple-chat-application
```

### 2. Compile the Code

#### On CentOS (Server):
```bash
gcc -o server server.c
```

#### On Fedora (Client):
```bash
gcc -o client client.c
```

### 3. Run the Server

On the CentOS machine, start the server by specifying the port number:
```bash
./server 5001
```
This will start the server listening on port `5001`.

### 4. Run the Clients

On each Fedora machine, start a client by specifying the server's hostname, the server port, and a local port for the client:
```bash
./client server_hostname 5001 5002
```

Replace `server_hostname` with the actual hostname or IP address of the CentOS server. Replace `5002` with the local port for the client.

### 5. Register and Start Chatting

- Upon starting, the client will prompt for a username and password.
- Once registered, the client will enter the chat session. Messages can be sent to the other connected client.
- Typing `Bye` will terminate the chat session.

### 6. Multiple Clients

The server is designed to handle two clients simultaneously. If a third client attempts to connect, they will receive a message indicating the chat is full and will need to wait.

## Example Usage

### Server Output:
```bash
Server is listening on port 5001...
Client 'Alice' connected
Client 'Bob' connected
Alice: Hello, Bob!
Bob: Hi, Alice! How are you?
```

### Client Output:
```bash
Enter username: Alice
Enter password: ********
Registration successful. You are now in the chat.
You: Hello, Bob!
Client: Hi, Alice! How are you?
```

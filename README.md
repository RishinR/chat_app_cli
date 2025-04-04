# Chat App CLI

This is a simple command-line chat application written in Rust, consisting of a server and multiple clients. The server handles incoming client connections and relays messages between them. Clients can connect, send messages, and receive messages from other connected clients.

## Features
- Multi-client support
- Non-blocking I/O for efficient handling of connections
- Message broadcasting to all connected clients
- Simple CLI-based interface

## Directory Structure
```
chat_app_cli/
├── server/    # Server implementation
├── client/    # Client implementation
```

## Running the Application

### 1. Start the Server
First, navigate to the `server` directory and run:
```sh
cargo run
```
The server will start listening on `127.0.0.1:6000` and wait for client connections.

### 2. Start a Client
Navigate to the `client` directory and run:
```sh
cargo run
```
You can start multiple clients by running the above command in separate terminals.

### 3. Sending Messages
- After running the client, you can type messages and press Enter to send them.
- Messages will be broadcasted to all connected clients.
- Type `:quit` to exit the chat.

## How It Works
- The **server** listens for incoming client connections and spawns a new thread for each client.
- Messages received from one client are broadcasted to all other clients.
- The **client** connects to the server, listens for incoming messages, and allows the user to send messages.
- The communication is handled using Rust’s multi-threading and message-passing capabilities via `mpsc` channels.

## Example Output
### Server Output
```
Client: 127.0.0.1:54321 connected!
127.0.0.1:54321: Hello!
127.0.0.1:65432: Hi there!
```

### Client Output
```
Write a message:
> Hello!
Message sent: "Hello!"
Message received: "Hi there!"
```

## Installation & Requirements
1. Install Rust using [rustup](https://rustup.rs/):
   ```sh
   curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
   ```
2. Clone this repository:
   ```sh
   git clone <repo_url>
   cd chat_app_cli
   ```
3. Run `cargo build` inside both `server` and `client` directories.

## License
This project is open-source and licensed under the MIT License.

## Contributions
Feel free to fork and submit pull requests to improve the functionality!


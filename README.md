# Rust Redis-like Server

This project is a simplified Redis-like server implemented in Rust. It supports basic key-value storage functionalities with optional key expiration and is capable of handling multiple client connections concurrently. This server is built to handle a subset of Redis commands and uses the Redis serialization protocol (RESP) for communication.

## Features

- **Basic Redis Commands**: Supports `PING`, `ECHO`, `SET`, and `GET` commands.
- **Concurrency**: Uses multithreading to handle multiple client connections simultaneously.
- **Key Expiration**: Allows setting expiration time for keys in milliseconds.
- **Error Handling**: Gracefully handles errors and client disconnections.

## Getting Started

### Running the Server

Run the server using Cargo:

    cargo run --release

The server will start and listen for connections on `127.0.0.1:6379`.

## Usage

Connect to the server using a Redis client or any compatible tool. Below are examples using `redis-cli`:
```
    redis-cli -p 6379
    127.0.0.1:6379> PING
    PONG
    127.0.0.1:6379> SET mykey myvalue
    OK
    127.0.0.1:6379> GET mykey
    "myvalue"
    127.0.0.1:6379> SET tempkey tempvalue PX 10000
    OK
    127.0.0.1:6379> ECHO "Hello, World!"
    "Hello, World!"
```

## Future Work

- **Replication**: leader follower (master-replica) replication


# Rock–Paper–Scissors Multiplayer – Socket Programming Project

This project implements a real-time multiplayer **Rock–Paper–Scissors** game using **C++ socket programming** over TCP connections. The system consists of a main server managing multiple rooms and clients connecting as players. The game is turn-based, time-sensitive, and demonstrates robust network programming concepts including concurrent connections, broadcasting, and room state management.

## Objectives

- Practice socket-level programming using `IPv4`, `TCP`, and both connection-oriented and connectionless models.
- Design a scalable server-client model supporting multiple game rooms and real-time interaction.
- Implement logic for room registration, game orchestration, and interactive communication.

## Game Overview

- Players join rooms and make their choice (rock, paper, or scissors) within 10 seconds.
- Each room can host **exactly two players**.
- The server collects the moves, determines the result, and broadcasts it.
- If one player fails to act in time, they automatically lose.

## Architecture

- `Main Server`: Listens for connections, handles room assignments and game logic.
- `Client`: Registers to a room and plays the game.
- Communication: Unicast for private messages, broadcast for game results.
- Room management supports join/leave actions and clean disconnection handling.

## Features

- Interactive CLI-based interface
- Support for up to N rooms (`N` given as launch argument)
- Broadcast messages for results
- Timeout and default loss logic
- Rejoin and replay support
- Supports commands like `/end_game` to terminate a room's game

## Build & Run

### Server

```bash
$ ./server.out {IP} {PORT} {#Rooms}
```

Example:
```bash
$ ./server.out 127.0.0.1 8080 5
```

### Client

```bash
$ ./client.out {IP} {PORT}
```

Example:
```bash
$ ./client.out 127.0.0.1 8080
```

## Key Technologies Used

- C++ sockets using `<sys/socket.h>` and `<netinet/in.h>`
- `fork`, `select`, and `poll` for multi-client handling
- Custom packet structure and string parsing
- `write`, `read`, `pipe`, `exec` for low-level IO

> Developed for the **Operating Systems** course – Fall 2024  
> University of Tehran | Department of Electrical and Computer Engineering  
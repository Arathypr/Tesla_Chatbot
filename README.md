# Spring Boot Chat Application

## Overview

This project is a Spring Boot application designed to provide real-time chat functionality using WebSockets. It supports sending messages and managing user sessions.

## Table of Contents

- [Overview](#overview)
- [Architecture](#architecture)
- [Getting Started](#getting-started)
- [Endpoints](#endpoints)
- [Dependencies](#dependencies)
- [Contributing](#contributing)
- [License](#license)

## Architecture

### Entities

- **ChatMessage**: Represents a chat message with content, sender, and type (CHAT, JOIN, LEAVE).

### Controllers

- **ChatController**: Handles sending messages and adding users.

### Configuration

- **WebSocketConfig**: Configures WebSocket endpoints and message broker.
- **WebSocketEventListener**: Listens for WebSocket events such as session disconnects.

## Getting Started

### Prerequisites

- Java 17 or higher
- Maven 3.6.0 or higher
- MySQL database

### Setup

1. **Clone the repository**
    ```bash
    git clone https://github.com/Arathypr/Tesla_Chatbot
    cd chatbot
    ```

2. **Configure the database**
    Update `application.properties` (or `application.yml`) with your MySQL database configurations.
    ```properties
    spring.datasource.url=jdbc:mysql://localhost:3306/yourdbname
    spring.datasource.username=yourusername
    spring.datasource.password=yourpassword
    spring.jpa.hibernate.ddl-auto=update
    ```

3. **Build and run the application**
    ```bash
    mvn clean install
    mvn spring-boot:run
    ```

### WebSocket Endpoint

- **WebSocket Endpoint**: `/ws` with SockJS fallback

## Endpoints

### ChatController

- **POST** `/app/chat.sendMessage`
    - Description: Send a chat message.
    - Payload: `ChatMessage` object.

- **POST** `/app/chat.addUser`
    - Description: Add a user to the chat.
    - Payload: `ChatMessage` object with the sender's name.

### Sample WebSocket Message

- **Message Structure**
    ```json
    {
        "content": "Hello, World!",
        "sender": "User1",
        "type": "CHAT"
    }
    ```

## Dependencies

- Spring Boot Starter Web
- Spring Boot Starter WebSocket
- MySQL Connector
- Lombok
- Spring Boot Starter Test

## Contributing

Contributions are welcome! Please fork the repository and create a pull request with your changes. Ensure that your code follows the existing code style and includes appropriate tests.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

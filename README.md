# 💬 Spring Boot WebSocket Chat App

![Java](https://img.shields.io/badge/Java-17-blue.svg)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.0-green.svg)
![WebSocket](https://img.shields.io/badge/WebSocket-enabled-orange.svg)

> A simple and scalable real-time chat application built with Spring Boot and WebSocket using STOMP messaging protocol.

---

## 📂 Project Structure

```
App/
├── src/
│   ├── main/
│   │   ├── java/com/chat/App/
│   │   │   ├── AppApplication.java
│   │   │   ├── config/WebSocketConfig.java
│   │   │   ├── controller/ChatController.java
│   │   │   └── model/ChatMessage.java
│   │   └── resources/
│   │       ├── application.properties
│   │       └── templates/chat.html
├── test/
│   └── java/com/chat/App/AppApplicationTests.java
├── pom.xml
```

---

## 🚀 Features

- ✅ Real-time messaging via WebSocket
- ✅ STOMP protocol support for message routing
- ✅ Simple frontend using HTML + JavaScript
- ✅ Auto-configured with Spring Boot
- ✅ Lightweight and extensible architecture

---

## 🛠️ Tech Stack

- **Java 17**
- **Spring Boot 3.x**
- **Spring WebSocket**
- **STOMP (Simple Text Oriented Messaging Protocol)**
- **Maven**
- **HTML5 / JavaScript**

---

## 🧰 Getting Started

### 🔗 Prerequisites

- Java 17 or higher
- Maven 3.x

### 📦 Installation

```bash
git clone https://github.com/your-username/springboot-websocket-chat.git
cd springboot-websocket-chat
```

### ▶️ Running the App

Use Maven wrapper:

```bash
./mvnw spring-boot:run
```

Or with Maven installed:

```bash
mvn spring-boot:run
```

Open your browser and go to:

```
http://localhost:8080
```

---

## 💡 How It Works

1. **Client** connects to WebSocket endpoint `/ws`.
2. Sends messages to `/app/chat` using STOMP.
3. Controller listens on `@MessageMapping("/chat")` and broadcasts via `@SendTo("/topic/messages")`.
4. Frontend subscribes to `/topic/messages` to receive live messages.

---

## ⚙️ Configuration

`application.properties`

```properties
spring.mvc.view.prefix=/templates/
spring.mvc.view.suffix=.html
```

`WebSocketConfig.java`

```java
registry.addEndpoint("/ws").withSockJS();
config.enableSimpleBroker("/topic");
config.setApplicationDestinationPrefixes("/app");
```

---

## 🧪 Testing

To run tests:

```bash
mvn test
```

For manual testing:
- Open multiple browser tabs to simulate multi-user chat.
- Use browser DevTools or WebSocket testing tools like [Postman](https://www.postman.com/) or Chrome plugins.

---

## 📌 Future Enhancements

- 🔐 Add user authentication
- 💾 Persist chat messages in a database (MySQL, MongoDB)
- 📱 Add frontend framework (React/Vue)
- 📊 Chat room support and private messaging
- 🌐 WebSocket load balancing with Redis or RabbitMQ

---

## 🤝 Contributing

Contributions are welcome! Feel free to fork the repo and submit a pull request.

### 🔧 Steps to Contribute

1. Fork the repository
2. Create a new branch: `git checkout -b feature-branch`
3. Commit your changes: `git commit -m "Add some feature"`
4. Push to the branch: `git push origin feature-branch`
5. Open a Pull Reqest

---

## 🙋‍♂️ Author

Developed by Yash Tripathi  
📧 yashtripathi0905@gmail.com

---

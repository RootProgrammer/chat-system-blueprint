# System Architecture Design

## 2.1 High-Level Architecture

- **Client-Server Model**: Continues to be the foundation, supporting communication between user
  devices (clients) and the server.

- **Microservices Architecture**: This approach remains optimal for scalability and maintainability,
  with Django and FastAPI powering different microservices based on their strengths.

## 2.2 Core Components

1. **Client Applications**:
    - **Web and Mobile Apps**: Developed with Flutter, which enables the creation of natively
      compiled applications for mobile, web, and desktop from a single codebase. This choice
      simplifies development and ensures consistency across platforms.

2. **Backend Services**:
    - **Authentication Service (Django)**: Utilizes Django's robust user management and
      authentication system to handle user sign-up, login, and security measures.
    - **Messaging Service (FastAPI)**: Leverages FastAPI for real-time messaging due to its high
      performance and support for asynchronous request handling, which is critical for real-time
      communication.
    - **Notification Service (Django)**: Django's comprehensive framework can efficiently manage
      notification logic, including web push notifications for real-time alerts.
    - **Media Service (FastAPI)**: FastAPI's asynchronous file handling capabilities make it
      suitable for managing media uploads and retrieval, ensuring efficient processing of images and
      videos.

3. **Database**:
    - **User Database (PostgreSQL)**: A relational database managed by Django ORM for storing user
      profiles, credentials, and settings.
    - **Message Database (MongoDB)**: A NoSQL database chosen for its flexibility in storing chat
      messages, used in conjunction with FastAPI for efficient, schema-less data storage.

4. **File Storage**:
    - Utilizes cloud storage services (like Amazon S3) for storing and serving media files shared in
      chats, integrated with both Django and FastAPI services.

5. **API Gateway**:
    - An API gateway that routes requests to the appropriate microservice, possibly using Nginx or a
      cloud service offering, ensuring a single entry point for enhanced security and easier
      management.

6. **Load Balancer**:
    - Balances incoming requests across the system's infrastructure to ensure high availability and
      reliability, critical for both Django and FastAPI services.

## 2.3 Communication Protocol

- **WebSocket**: For real-time, bidirectional communication. FastAPI offers native support for
  WebSocket, making it ideal for the messaging service to instantly deliver messages between users.
- **HTTP/REST API**: Both Django and FastAPI will expose RESTful endpoints for operations like user
  registration, profile updates, and non-real-time data requests.

## 2.4 Data Storage and Management

- **PostgreSQL**: Managed by Django for relational data such as user accounts and relationships.
- **MongoDB**: Used with FastAPI for storing chat messages, leveraging its performance and
  flexibility for unstructured data.
- **Redis**: Acts as a cache and session store, improving response times and reducing load on the
  primary databases.

## 2.5 Security Considerations

- **HTTPS**: Ensures secure communication over the internet, encrypting data in transit.
- **JWT for Authentication**: Both Django and FastAPI can implement JWT for secure, token-based user
  authentication and session management.
- **Data Encryption**: Applying encryption to sensitive data both in transit and at rest, with
  special attention to end-to-end encryption for messages.

## Conclusion

Adapting the system architecture to include Flutter, Django, and FastAPI offers a robust, scalable,
and efficient foundation for developing a cross-platform chat system. This revised architecture
takes advantage of Flutter's cross-platform capabilities, Django's robustness and ease of use for
standard web services, and FastAPI's performance in real-time communication and media handling. The
next steps would involve detailed planning for each component, defining the development workflow,
and setting up the development environment to start implementation.

![Candidate Engagement Bot System Design](https://raw.githubusercontent.com/sachanarpit/assignments-fullstack/c1d7dcf70546c3081e7fc99e6ea3745a4b7bda90/system_design.svg)

## Explanation of the System Design Chart

### Client

- **React Frontend**:
  - The user interface where candidates interact with the chatbot.
  - Communicates with the backend securely over HTTPS.

### Server

- **Load Balancer**:
  - Distributes incoming traffic across multiple Node.js backend instances for scalability and high availability.
- **Node.js Backend Instances**:
  - Handle API requests from the frontend.
  - Integrate with the OpenAI API for natural language processing.
  - Interact with the MongoDB Cluster for persistent data storage.
- **Redis Cache**:
  - Stores frequently accessed data (e.g., candidate profiles, recent chat history) to reduce database load and improve response times.
- **MongoDB Cluster**:
  - Stores persistent data such as user credentials, conversation history, and candidate profiles.
  - Supports sharding for scalability.
- **OpenAI API**:
  - Provides natural language processing capabilities for the chatbot.

### Security

- **JWT Authentication**:
  - Ensures only authenticated users can access the system.
- **HTTPS Encryption**:
  - Secures all communications between the client and server.
- **Role-Based Access Control (RBAC)**:
  - Enforces permissions within the backend, restricting access to authorized data only.

### Scalability

- **Horizontal Scaling**:
  - Allows the system to handle increased load by adding more backend instances.
- **MongoDB Sharding**:
  - Distributes database data across multiple servers for horizontal scalability.

### Database Collections

- **Users**:
  - Stores user credentials and roles.
- **Conversations**:
  - Stores chat history for each user.
- **Profiles**:
  - Stores extracted candidate qualifications.

This design ensures the Candidate Engagement Chatbot is secure, scalable, and maintainable, providing an efficient and reliable experience for users.

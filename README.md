# lient-Server-Pattern-and-REST-API-Design

### **CS 230 Module Four Journal: Client-Server Pattern and REST API Design**

**Client-Server Pattern in Software Requirements**

The client-server architectural pattern is a fundamental software design model that effectively separates the concerns of a software system into two independent tiers: the client (frontend) and the server (backend). This separation allows for scalability, flexibility, and cross-platform support—key considerations for developing a web-based game like *Draw It or Lose It*. In this model, the client handles the presentation and user interaction layer, while the server manages business logic, authentication, authorization, and data storage.

By applying this pattern, we can ensure that the *Draw It or Lose It* application is no longer restricted to Android alone, but is instead capable of being deployed across multiple platforms such as desktop browsers, iOS devices, or gaming consoles. The use of RESTful APIs allows client platforms to communicate with a common server, ensuring consistency in behavior and data handling. This modularity enables independent updates and improvements to either side of the application without affecting the other.

**Server-Side Implementation and REST API**

In this module, we focused on developing the server side of the application using Dropwizard and Java. The server exposes endpoints via a RESTful API, which clients can consume regardless of their platform. REST (Representational State Transfer) is particularly effective here due to its simplicity, statelessness, and platform-agnostic structure.

We implemented basic authentication to protect sensitive resources and used role-based authorization to control user access. For example, users with the “ADMIN” role could create new game users, while those with the “USER” role could only retrieve user details. This approach mimics real-world web applications where access rights differ depending on a user’s role, improving both security and clarity of functionality.

The server provides JSON responses to HTTP GET and POST requests, allowing any frontend—whether a browser, mobile app, or game console—to parse and interact with the backend using standard web protocols. Furthermore, this server implementation allows future replacement or enhancement of the authentication system (e.g., moving to OAuth 2.0) without rewriting client code, demonstrating the value of cleanly separated tiers.

**Client-Side Interaction and Considerations**

Though the majority of the work in this assignment was server-focused, it is important to understand what is required from the client side to integrate with the REST API. A client application—whether built with JavaScript (React), Swift (iOS), or Unity (for gaming platforms)—must be able to:

* Send authenticated HTTP requests to the server
* Interpret and render JSON responses from the server
* Handle errors such as 403 (unauthorized) or 404 (not found)

To support all three initial clients (e.g., web, iOS, Android), frontend developers would need to create API clients for each platform that conform to the server’s authentication and data exchange model. Developers would also need to design intuitive interfaces that align with the platform’s UI conventions while maintaining a consistent experience across devices.

**Next Steps for Client-Side Expansion**

To evolve the application further, several tasks would be required:

1. **Adding More Users to the Database:**

   * Implement a registration interface on the client.
   * Extend the server to accept new user data (possibly using a secure admin-only endpoint).
   * Add persistent storage using a relational database like MySQL or PostgreSQL instead of hardcoded user lists.

2. **Additional Game Features:**

   * Timer countdown for drawing rounds
   * Real-time team score tracking
   * Chat or voice integration for team communication
   * Leaderboards and multiplayer matchmaking

3. **Expanding to New Platforms (e.g., Xbox and PS4):**

   * Develop client apps using game development engines like Unity or Unreal Engine, which can deploy to both Xbox and PS4.
   * Ensure the game client supports HTTPS communication and JSON parsing.
   * Maintain shared session and user state across platforms using secure tokens or cookies.

By using REST and maintaining a clear client-server separation, we make this level of platform expansion technically feasible without needing to redevelop the core business logic of the application.

---

**Conclusion**

The client-server pattern, enhanced by REST APIs, offers an efficient and scalable path to modern multi-platform applications. In this module, we built a secure backend that handles user management and role-based access for *Draw It or Lose It*. This foundation positions the application for future enhancements, additional features, and cross-platform deployments. While further work is needed on the frontend and hosting, the modularity and extensibility of our current architecture ensure that each tier can evolve independently while remaining tightly integrated through standardized interfaces.

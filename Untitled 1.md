
# **Online Collaborative Whiteboard: System Design and Implementation (Proposed)**

## **Abstract**

This document proposes the design and future implementation of an online collaborative whiteboard application. The system will be a web-based tool enabling real-time multi-user drawing and live chat, intended to demonstrate proficiency in modern full-stack development. The proposed front end will be built using React, leveraging the HTML5 Canvas API to support drawing tools such as a freehand pencil, geometric shapes, and color/thickness selection. The back end is planned to be implemented in Python (FastAPI or Flask) to support auxiliary services like real-time chat via WebSockets. Firebase will be integrated for Realtime Database services and Authentication, enabling serverless data synchronization and user management. The system architecture aims to combine client-side rendering with cloud-managed data sync to ensure low-latency updates and offline support. This capstone project is currently under development and is intended to showcase technical skills in frontend frameworks, backend APIs, real-time protocols, and cloud integration.

---

## **1. Introduction**

With the increasing demand for remote learning and virtual collaboration, online whiteboard tools have become indispensable. These platforms allow distributed users to sketch, annotate, and interact visually in real-time. Inspired by existing commercial solutions such as Google Jamboard, Miro, and Microsoft Whiteboard, this proposed project seeks to design and develop a custom collaborative whiteboard system from the ground up to gain a deeper understanding of the underlying technologies and real-time system design.

### **Problem Statement**

Despite the availability of mature commercial tools, building a real-time collaborative whiteboard from scratch provides significant educational value. The proposed problem is to design a system that allows multiple users to draw on a shared digital canvas in real-time with features such as freehand and shape drawing, color/thickness control, and integrated live chat. The system must address challenges related to concurrent input handling, network latency, and user management.

### **Objectives**

The key objectives of this proposed project are:

- Design a responsive, real-time collaborative whiteboard that supports freehand and geometric shape drawing.
    
- Provide user-configurable drawing tools, including color and stroke width options.
    
- Enable real-time synchronization of drawing data across multiple users.
    
- Integrate a live chat system for in-session communication.
    
- Develop a React-based front-end using component-driven architecture.
    
- Implement backend services in Python (FastAPI or Flask) to manage WebSocket-based chat.
    
- Use Firebase Realtime Database and Authentication for cloud-based data sync and user access control.
    
- Demonstrate integration of front-end, back-end, and cloud services in a scalable architecture.
    

---

## **2. Literature Review and Background**

### **Collaborative Whiteboards in Education**

Previous research highlights the value of interactive whiteboards in educational settings. According to BECTA (2004) and Smith et al. (2005), such tools improve student engagement and concept retention. Bannon and Parnell (2012) emphasize that features such as customizable tools enhance learning experiences. These insights inform our proposed features like multiple drawing tools and customization options, which aim to support use cases like brainstorming, diagramming, and interactive note-taking.

### **Real-Time Collaboration Technologies**

#### **React**

React's declarative and component-based structure makes it suitable for building highly interactive UIs. In this project, React will be used to manage UI states, drawing tools, and canvas rendering logic.

#### **Python Back-End**

FastAPI or Flask will be considered for setting up WebSocket and REST API endpoints to handle real-time communication and auxiliary services like snapshot saving.

#### **WebSockets**

WebSockets offer persistent bi-directional communication ideal for real-time chat. The backend server will maintain active WebSocket sessions and broadcast messages to all participants efficiently.

#### **Firebase Realtime Database and Authentication**

Firebase’s Realtime Database will be used to store and synchronize drawing data, while Firebase Authentication will ensure secure user access. This combination offloads complex backend logic and facilitates rapid development.

---

## **3. Proposed System Design and Architecture**

The application architecture is designed with modularity and scalability in mind. Below is a conceptual overview of the components:

### **React Front-End (Client-Side)**

- **Canvas Component**: Captures drawing input via mouse/touch events.
    
- **Toolbar**: Allows users to select tools, colors, and stroke widths.
    
- **Chat Box**: Facilitates real-time text communication.
    
- **State Management**: Uses React hooks and context to manage tool states and drawing actions.
    

### **Firebase Realtime Database**

- Stores drawing strokes in a structured JSON format under `rooms/{roomId}/strokes`.
    
- Real-time updates are propagated to all connected clients using Firebase SDK listeners.
    
- Provides offline persistence and automatic conflict resolution.
    

### **Python WebSocket Server**

- Manages WebSocket connections for the chat feature.
    
- A `ConnectionManager` class will track clients and broadcast messages.
    
- Optionally exposes REST APIs for saving board snapshots or analytics.
    

### **Authentication**

- Firebase Authentication will manage user identity using email/password or third-party sign-ins.
    
- Access rules in the Firebase database will enforce data security.
    

---

## **4. Data Flow and User Interaction (Proposed)**

1. **Drawing Flow**:
    
    - User A draws on canvas.
        
    - Stroke data (coordinates, color, width, user ID, timestamp) is pushed to Firebase.
        
    - Firebase synchronizes the data in real time with all connected clients.
        
    - React components on other clients receive the update and render the stroke.
        
2. **Chat Flow**:
    
    - User B types a message.
        
    - Message is sent via WebSocket to the Python server.
        
    - Server broadcasts the message to all clients’ chat components.
        

---

## **5. Scalability and Sharding Strategy**

Each session (or "room") will be isolated within the database, enabling horizontal scaling by sharding sessions across different Firebase database instances if needed. This stateless design allows for dynamic scalability while maintaining data consistency and performance.

---


## **8. Conclusion**

This project is currently under development and aims to deliver a fully functional, scalable, and intuitive collaborative whiteboard system. By leveraging modern frontend, backend, and cloud technologies, it not only targets practical usability but also serves as a comprehensive learning experience in real-time system design.

---


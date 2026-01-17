```md
# Tasks API Assignment 3 

This project is a backend CRUD API for managing tasks.  
It was developed as part of Assignment 3 and demonstrates the use of MongoDB Atlas for data persistence, Express.js for API development, and Postman for testing.

---

##  Project Description

The goal of this project is to evolve a backend application from simple local storage to a cloud-based database using MongoDB Atlas.  
The API allows users to create, read, update, and delete tasks. Each task contains multiple required fields and is stored permanently in the database.

This project represents a basic task management system and can be used as a foundation for a larger full-stack application.

---

##  Technologies Used

- **Node.js** – JavaScript runtime environment  
- **Express.js** – Web framework for building REST APIs  
- **MongoDB Atlas** – Cloud-based NoSQL database  
- **Mongoose** – ODM library for MongoDB  
- **Postman** – API testing tool  
- **HTML & JavaScript** – Simple frontend interface  

---

##  Project Structure

The project was implemented without separate folders to keep the structure simple.

```

assignment3_tasks/
│
├── server.js         
├── index.html        
├── package.json      
├── package-lock.json 
└── README.md          

```

---

##  Data Model (Task Schema)

Each task in the database contains the following fields:

| Field        | Type    | Required | Description |
|--------------|---------|----------|-------------|
| title        | String  | Yes      | Task title |
| description  | String  | Yes      | Task description |
| priority     | String  | Yes      | Task priority (low, medium, high) |
| completed    | Boolean | No       | Task completion status |
| createdAt   | Date    | Auto     | Creation timestamp |
| updatedAt   | Date    | Auto     | Last update timestamp |

Mongoose timestamps are used to automatically generate `createdAt` and `updatedAt`.

---

##  API Endpoints

###  Create a Task
```

POST /tasks

````
**Request Body (JSON):**
```json
{
  "title": "Prepare presentation",
  "description": "Create slides for the final project defense",
  "priority": "medium"
}
````

**Response:**

* Status: `201 Created`
* Returns the created task object

---

###  Get All Tasks

```
GET /tasks
```

**Response:**

* Status: `200 OK`
* Returns an array of all tasks

---

###  Get Task by ID

```
GET /tasks/:id
```

**Response:**

* Status: `200 OK` if found
* Status: `404 Not Found` if task does not exist

---

###  Update a Task

```
PUT /tasks/:id
```

**Request Body (JSON example):**

```json
{
  "completed": true
}
```

**Response:**

* Status: `200 OK`
* Returns the updated task

---

###  Delete a Task

```
DELETE /tasks/:id
```

**Response:**

* Status: `200 OK`
* Confirmation message

---

##  Testing

All API endpoints were tested manually using **Postman**.
The following aspects were verified:

<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 18 30" src="https://github.com/user-attachments/assets/fea6f487-919c-4e9f-824c-a0d241223d6e" />
<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 18 06" src="https://github.com/user-attachments/assets/827e67e8-f75f-478b-8c36-e32fa44eb53f" />
<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 17 31" src="https://github.com/user-attachments/assets/c568ed02-26b3-4ff6-b177-a4e1e4507b22" />
<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 16 51" src="https://github.com/user-attachments/assets/6bbbcc03-5783-4991-83f8-09aa1eb93429" />
<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 15 01" src="https://github.com/user-attachments/assets/fc82b3c7-61be-4e1e-b3a8-8dfd52664044" />
<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 25 36" src="https://github.com/user-attachments/assets/a0b6d3d3-8b27-4208-b7ef-69229565616a" />

---

##  Simple Interface

A basic HTML interface (`index.html`) was created to interact with the API.
The interface allows users to:

* Add new tasks
* View the list of existing tasks

<img width="1440" height="900" alt="Снимок экрана 2026-01-17 в 19 25 41" src="https://github.com/user-attachments/assets/25739373-64f8-4ff7-ae9b-9c03302abc1b" />

---

##  How to Run the Project

1. Install dependencies:

```
npm install
```

2. Start the server:

```
node server.js
```

3. Open in browser:

```
http://localhost:3000/
```

4. Test endpoints using Postman:

```
http://localhost:3000/tasks
```

---

##  Database

MongoDB Atlas is used as a cloud database.
Network access was configured by adding the client IP address, and a database user with read/write permissions was created.

---

##  Conclusion

This project helped improve understanding of backend development with Express and MongoDB.
It demonstrated how to design a data schema, implement full CRUD functionality, connect to a cloud database, and test APIs using Postman.
The assignment provided practical experience in building a real-world backend application.

---

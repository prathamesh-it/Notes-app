# 📝 Notes App — Full Stack CRUD Application

A simple Notes taking application built with **Spring Boot** (Backend) and **React** (Frontend) with full CRUD operations.

---

## 🛠️ Tech Stack

### Backend
| Technology | Purpose |
|---|---|
| Java 17 | Programming Language |
| Spring Boot | Backend Framework |
| Spring Data JPA | Database ORM |
| PostgreSQL | Database |
| Lombok | Reduce Boilerplate Code |
| Maven | Build Tool |

### Frontend
| Technology | Purpose |
|---|---|
| React | Frontend Framework |
| Vite | Build Tool |
| Axios | HTTP Requests |
| Bootstrap | UI Styling |

---

## 📁 Project Structure

### Backend
```
notes-backend/
│
├── src/main/java/com/example/notes/
│   ├── controller/
│   │   └── NoteController.java
│   ├── model/
│   │   └── Note.java
│   ├── repository/
│   │   └── NoteRepository.java
│   ├── service/
│   │   └── NoteService.java
│   └── NotesApplication.java
│
├── src/main/resources/
│   └── application.properties
│
└── pom.xml
```

### Frontend
```
notes-frontend/
│
├── src/
│   ├── components/
│   │   ├── NoteList.jsx
│   │   ├── NoteForm.jsx
│   │   └── NoteCard.jsx
│   ├── services/
│   │   └── noteService.js
│   ├── App.jsx
│   └── main.jsx
│
└── package.json
```

---

## 🚀 Getting Started

### Prerequisites
- Java 17+
- Node.js 18+
- PostgreSQL
- Maven

---

### 1. Clone the Repository
```bash
git clone https://github.com/your-username/notes-app.git
cd notes-app
```

---

### 2. Setup PostgreSQL Database
```sql
CREATE DATABASE notesdb;
```

---

### 3. Configure Backend

Update `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/notesdb
spring.datasource.username=your_username
spring.datasource.password=your_password

spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.dialect=org.hibernate.dialect.PostgreSQLDialect
```

---

### 4. Run the Backend
```bash
cd notes-backend
./mvnw spring-boot:run
```
Backend will start at `http://localhost:8080`

> ✅ Spring Boot will automatically create the `notes` table in PostgreSQL on startup.

---

### 5. Run the Frontend
```bash
cd notes-frontend
npm install
npm run dev
```
Frontend will start at `http://localhost:5173`

---

## 📡 API Endpoints

Base URL: `http://localhost:8080/api/notes`

| Method | Endpoint | Description |
|---|---|---|
| GET | `/api/notes` | Get all notes |
| GET | `/api/notes/{id}` | Get note by ID |
| POST | `/api/notes` | Create a new note |
| PUT | `/api/notes/{id}` | Update a note |
| DELETE | `/api/notes/{id}` | Delete a note |

---

## 📨 Sample API Requests

### Create Note (POST)
```json
{
    "title": "My First Note",
    "content": "This is my note content"
}
```

### Update Note (PUT)
```json
{
    "title": "Updated Title",
    "content": "Updated content"
}
```

### Sample Response
```json
{
    "id": 1,
    "title": "My First Note",
    "content": "This is my note content",
    "createdAt": "2026-06-07T10:00:00",
    "updatedAt": "2026-06-07T10:00:00"
}
```

---

## ✨ Features

- ✅ Create a new note
- ✅ View all notes
- ✅ View a single note
- ✅ Update an existing note
- ✅ Delete a note
- ✅ Auto timestamps (createdAt, updatedAt)
- ✅ Responsive UI with Bootstrap

---

## 🗄️ Database Schema

Table: `notes`

| Column | Type | Description |
|---|---|---|
| id | BIGINT | Primary Key, Auto Increment |
| title | VARCHAR | Note title |
| content | TEXT | Note content |
| created_at | TIMESTAMP | Auto set on create |
| updated_at | TIMESTAMP | Auto set on update |

---
## 📄 License

This project is open source and available under the [MIT License](LICENSE).

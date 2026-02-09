# 📱 Social MVP – Social Network with Flutter & Node.js

> MVP project of a social network featuring authentication, friendships, feed, real-time chat, and online presence.

---

## 📌 About the Project

This project is a **Minimum Viable Product (MVP)** of a social network developed with **Flutter** on the frontend and **Node.js** on the backend.

It implements core social media features such as user authentication, profile management, friendships, private real-time chat via WebSockets, image-based posts, and online/offline presence tracking.

The main goal of this project is **academic learning and hands-on experience** with fullstack development, real-time communication, and modern application architecture.

---

## 🚀 Technologies Used

### 📱 Frontend (Flutter)

- Flutter SDK ^3.8.1
- `http` – REST API requests
- `shared_preferences` – Local storage
- `provider` – State management
- `go_router` – Declarative navigation
- `web_socket_channel` – Real-time communication
- `image_picker` – Image selection
- `jwt_decoder` – JWT token decoding
- Internationalization (`flutter_localizations`, `flutter_gen`)
- `http_parser`, `path`, `cupertino_icons`

### 🌐 Backend (Node.js + Express)

- `express` – Web framework
- `sequelize` + `pg` – ORM with PostgreSQL
- `jsonwebtoken` – JWT authentication
- `bcryptjs` – Password hashing
- `multer` – File uploads
- `sharp` – Image resizing and optimization
- `nodemailer` – Password recovery emails
- `ws` – Native WebSocket server
- `dotenv`, `cors`, `uuid`, `express-validator`

---

## 🧪 Features

### Authentication & User Management
- User registration
- Login with JWT authentication
- Update nickname, username, and password
- Profile photo upload
- Password recovery via verification code

### Friendships
- Search users by nickname
- Send, accept, or reject friend requests
- List friends and pending requests

### Feed
- Create image-based posts
- View posts feed

### Private Chat
- One-to-one private chat between friends
- Real-time message exchange using WebSockets

### Online Presence
- Real-time online/offline status updates

### Settings
- Responsive layout
- Language selection
- Theme mode (dark or light)
- Update profile information
- Logout

---

## 📂 Backend Routes Structure

| Resource      | Method | Route                                       | Description                              |
|---------------|--------|---------------------------------------------|------------------------------------------|
| Auth          | POST   | `/users/register`                           | Register a new user                      |
|               | POST   | `/users/login`                              | User login                               |
|               | PUT    | `/users/nickname`                           | Update nickname                          |
|               | PUT    | `/users/username`                           | Update username                          |
|               | PUT    | `/users/password`                           | Update password                          |
| Upload        | POST   | `/uploads/uploadProfilePhoto`               | Upload profile picture                  |
| Friendships   | GET    | `/friendships/getFriends`                   | List friends                             |
|               | GET    | `/friendships/searchByNickname/:nickname`   | Search users by nickname                |
|               | POST   | `/friendships/sendFriendRequest`            | Send friend request                     |
|               | GET    | `/friendships/getPendingFriendRequests`     | Received friend requests                |
|               | POST   | `/friendships/respondToFriendRequest`       | Accept or reject request                |
|               | GET    | `/friendships/getSentPendingFriendRequests` | Sent pending requests                   |
| Feed          | POST   | `/posts/post`                               | Create post with image                  |
|               | GET    | `/posts/feed`                               | Get posts feed                          |
| Chat          | GET    | `/chats/me`                                 | List user chats                         |
|               | GET    | `/chats/private/:friendId`                  | Create or access private chat           |
|               | GET    | `/chats/:chatId/messages`                   | Get chat messages                      |
|               | POST   | `/chats/:chatId/messages`                   | Send message                            |
| Recovery      | POST   | `/codes/request`                            | Request password recovery code          |
|               | POST   | `/codes/verify`                             | Verify recovery code                   |
|               | POST   | `/codes/resetPass`                          | Reset password                         |
| Presence      | PUT    | `/presence/updatePresence`                  | Update online/offline status            |

---

## ⚙️ Installation & Execution

### 1. Clone the repository

```bash
git clone https://github.com/your-username/your-repo.git
cd your-repo
```

---

### 2. Environment Variables

Create a `.env` file:

```bash
# Database configuration
DB_NAME=oprime
DB_USER=postgres
DB_PASS=root
DB_HOST=localhost
DB_PORT=5432

# API configuration
API_PORT=3000

# JWT configuration
JWT_SECRET=root

# Email configuration
EMAIL_SERVICE=gmail
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=your@gmail.com
SMTP_PASS=your_password
```

---

### 3. Backend (Node.js)

```bash
cd backend
npm install
npm run dev
```

---

### 4. Frontend (Flutter)

```bash
cd app
flutter pub get
flutter run -d edge
```

---

## 📡 Real-Time Communication

- Uses `web_socket_channel` (Flutter) and `ws` (Node.js) for private chat.
- Online presence is synchronized in real time through WebSocket connections.

---

## 📁 Project Structure

```
/app               # Flutter (Frontend)
  └── lib/
      └── pages/
      └── services/
      └── l10n/
      └── main.dart

/backend           # Node.js (Backend)
  └── routes/
  └── controllers/
  └── models/
  └── config/
  └── servers.js
```

---

## ✅ Automated Tests

Run backend tests:

```bash
npm run tests
```

---

## 🛡️ Authentication

All protected routes use JWT middleware.  
The token is stored in the Flutter app using `SharedPreferences` and sent via the `Authorization` header.

---

## 📄 Author

**Eduardo Cardoso Agostinetti**  
Developed for academic and learning purposes.

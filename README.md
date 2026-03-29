<h1 align="center">
  <br>
  📝 Blogify
  <br>
</h1>

<h4 align="center">A full-stack blogging platform built with <a href="https://nodejs.org" target="_blank">Node.js</a>, <a href="https://expressjs.com" target="_blank">Express</a>, <a href="https://www.mongodb.com" target="_blank">MongoDB</a>, and <a href="https://ejs.co" target="_blank">EJS</a>.</h4>

<p align="center">
  <img src="https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white" alt="Node.js"/>
  <img src="https://img.shields.io/badge/Express.js-000000?style=for-the-badge&logo=express&logoColor=white" alt="Express.js"/>
  <img src="https://img.shields.io/badge/MongoDB-4EA94B?style=for-the-badge&logo=mongodb&logoColor=white" alt="MongoDB"/>
  <img src="https://img.shields.io/badge/EJS-B4CA65?style=for-the-badge&logo=ejs&logoColor=black" alt="EJS"/>
  <img src="https://img.shields.io/badge/Bootstrap-563D7C?style=for-the-badge&logo=bootstrap&logoColor=white" alt="Bootstrap"/>
</p>

<p align="center">
  <a href="#-features">Features</a> •
  <a href="#-tech-stack">Tech Stack</a> •
  <a href="#-project-structure">Project Structure</a> •
  <a href="#-getting-started">Getting Started</a> •
  <a href="#-environment-variables">Environment Variables</a> •
  <a href="#-api-routes">API Routes</a> •
  <a href="#-contributing">Contributing</a> •
  <a href="#-license">License</a>
</p>

---

## ✨ Features

- 🔐 **User Authentication** — Secure sign-up & login with salted password hashing
- 👤 **Role-Based Access Control** — Separate `USER` and `ADMIN` roles with distinct permissions
- 📝 **Blog Management** — Create, read, update, and delete blog posts with ease
- 🖼️ **Profile Images** — Default avatar support with custom profile picture upload
- 📱 **Responsive UI** — Mobile-friendly dark-themed navbar powered by Bootstrap 5
- ⚡ **Fast & Lightweight** — Minimal dependencies for blazing-fast performance
- 🗃️ **MongoDB Integration** — Persistent data storage via Mongoose ODM with timestamps

---

## 🛠️ Tech Stack

| Layer        | Technology                          |
|--------------|-------------------------------------|
| Runtime      | Node.js                             |
| Framework    | Express.js v5                       |
| Database     | MongoDB + Mongoose v9               |
| Templating   | EJS v5                              |
| UI Framework | Bootstrap 5 (Dark Theme)            |
| Dev Tools    | Nodemon                             |

---

## 📁 Project Structure

```
YOUTUBE-BLOG/
├── controllers/          # Business logic for routes
├── models/
│   └── user.js           # Mongoose User schema (auth, roles, profile)
├── public/
│   └── images/           # Static assets (default avatars, etc.)
├── routes/               # Express route definitions
├── views/
│   ├── home.ejs          # Home page template
│   └── partials/
│       ├── head.ejs      # Common <head> meta & CSS imports
│       ├── nav.ejs       # Responsive navigation bar
│       └── scripts.ejs   # Common JS imports
├── index.js              # App entry point & server bootstrap
├── package.json          # Project metadata & dependencies
└── .env                  # Environment variables (not committed)
```

---

## 🚀 Getting Started

### Prerequisites

Ensure you have the following installed on your machine:

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [MongoDB](https://www.mongodb.com/) (local instance or [MongoDB Atlas](https://www.mongodb.com/cloud/atlas))

### Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/your-username/youtube-blog.git
   cd youtube-blog
   ```

2. **Install dependencies**

   ```bash
   npm install
   ```

3. **Configure environment variables**

   Create a `.env` file in the root directory. See [Environment Variables](#-environment-variables) for required fields.

4. **Start the development server**

   ```bash
   npm run dev
   ```

   The application will be running at **http://localhost:8000**

5. **For production**

   ```bash
   npm start
   ```

---

## 🔑 Environment Variables

Create a `.env` file in the project root with the following variables:

```env
# Server
PORT=8000

# Database
MONGO_URI=mongodb://localhost:27017/blogify

# Authentication
SESSION_SECRET=your_super_secret_key_here
```

> ⚠️ **Never commit your `.env` file to version control.** It is already listed in `.gitignore`.

---

## 🗺️ API Routes

> ℹ️ Routes are actively being developed. Below is the planned structure.

| Method | Endpoint              | Description                    | Auth Required |
|--------|-----------------------|--------------------------------|---------------|
| `GET`  | `/`                   | Render the home / blog feed    | No            |
| `GET`  | `/user/signup`        | Render sign-up page            | No            |
| `POST` | `/user/signup`        | Register a new user            | No            |
| `GET`  | `/user/signin`        | Render sign-in page            | No            |
| `POST` | `/user/signin`        | Authenticate and log in user   | No            |
| `GET`  | `/user/logout`        | Log out the current user       | Yes           |
| `GET`  | `/blog/add`           | Render new blog form           | Yes           |
| `POST` | `/blog/add`           | Create a new blog post         | Yes           |
| `GET`  | `/blog/:id`           | View a single blog post        | No            |

---

## 🧩 Data Models

### User

| Field             | Type     | Required | Default          | Notes                        |
|-------------------|----------|----------|------------------|------------------------------|
| `fullName`        | String   | ✅        | —                | User's full display name     |
| `email`           | String   | ✅        | —                | Unique identifier            |
| `salt`            | String   | ✅        | —                | Used for password hashing    |
| `password`        | String   | ✅        | —                | Hashed password (never plain)|
| `profileImageURL` | String   | ❌        | `/images/man.png`| Avatar URL                   |
| `role`            | String   | ❌        | `USER`           | Enum: `USER`, `ADMIN`        |
| `createdAt`       | Date     | Auto     | —                | Mongoose timestamp           |
| `updatedAt`       | Date     | Auto     | —                | Mongoose timestamp           |

---

## 🤝 Contributing

Contributions are welcome! To get started:

1. Fork the repository
2. Create a new branch: `git checkout -b feature/your-feature-name`
3. Make your changes and commit: `git commit -m 'feat: add your feature'`
4. Push to the branch: `git push origin feature/your-feature-name`
5. Open a Pull Request

Please follow [Conventional Commits](https://www.conventionalcommits.org/) for commit messages.

---

## 📄 License

This project is licensed under the **ISC License**. See the [LICENSE](LICENSE) file for details.

---

<p align="center">
  Made with ❤️ while following along with <a href="https://www.youtube.com/@piyushgargdev">Piyush Garg</a> on YouTube.
</p>

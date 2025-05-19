# 🌍 MultiUser Globe Tracker

**MultiUser Globe Tracker** is a collaborative world map application where multiple users (e.g., family or friends) can mark the countries they've visited. Each user is assigned a unique color, and their selected countries are highlighted accordingly on an interactive SVG world map.

This project combines a dynamic frontend with a PostgreSQL-powered backend to store and update user selections in real time.

---

## ✨ Features

- 👥 Add multiple users with custom names and colors
- 🗺️ Interactive world map for country selection
- 🎨 Each user’s selected countries are colored uniquely
- 💾 Persistent data storage using PostgreSQL
- ✅ Supports **Create**, **Read**, and **Update** operations

---

## 🛠 Tech Stack

### Frontend
- HTML, CSS, JavaScript
- EJS (Embedded JavaScript Templates)
- SVG for world map rendering

### Backend
- Node.js
- Express.js

### Database
- PostgreSQL
- `pg` Node.js package for querying

---

## 📁 Folder Structure

```plaintext
MultiUser-Globe-Tracker/
├── public/
│   └── styles/
│       └── style.css
├── views/
│   ├── index.ejs
│   └── partials/
│       └── header.ejs
├── db/
│   └── connection.js        # PostgreSQL DB config
├── index.js                 # Express server
├── package.json
└── README.md

setup_instructions:
  prerequisites:
    - Node.js installed
    - PostgreSQL installed and running

  steps:
    - step: "Clone the Repository"
      commands:
        - git clone https://github.com/aryan-0069/MultiUser-Globe-Tracker.git
        - cd MultiUser-Globe-Tracker

    - step: "Install Dependencies"
      commands:
        - npm install

    - step: "Setup PostgreSQL Database"
      instructions:
        - Create a database, e.g., 'family_tracker'
        - Run the following SQL schema:
          |
          CREATE TABLE users (
            id SERIAL PRIMARY KEY,
            name TEXT NOT NULL,
            color TEXT NOT NULL
          );

          CREATE TABLE country_selections (
            id SERIAL PRIMARY KEY,
            user_id INTEGER REFERENCES users(id),
            country_code TEXT NOT NULL
          );

    - step: "Configure Database Credentials"
      instructions:
        - Edit 'db/connection.js' with your PostgreSQL configuration:
          |
          const pool = new Pool({
            user: 'your_username',
            host: 'localhost',
            database: 'family_tracker',
            password: 'your_password',
            port: 5432,
          });

    - step: "Start the Server"
      commands:
        - node index.js

    - step: "Open the App"
      instructions:
        - Visit: http://localhost:3000

🌍 MultiUser Globe Tracker
MultiUser Globe Tracker is an interactive web application where multiple users (such as family members or friends) can mark countries on a shared world map. Each user is given a distinct color, and their selected countries appear on the map in that color — making it perfect for tracking global travel together!

🚀 Features
🧑‍🤝‍🧑 Add multiple users with names and colors

🗺️ Interactive SVG world map for selecting countries

🎨 Color-coded country tracking per user

💾 PostgreSQL database to store users and their selected countries

🔁 Full Create, Read, and Update functionality for map data

🛠️ Tech Stack
Frontend:

HTML, CSS, JavaScript

EJS templates

SVG for the interactive world map

Backend:

Node.js

Express.js

Database:

PostgreSQL using pg Node.js package

📂 Project Structure
pgsql
Copy
Edit
MultiUser-Globe-Tracker/
├── public/
│   └── styles/
│       └── style.css
├── views/
│   ├── index.ejs
│   └── partials/
│       └── header.ejs
├── db/
│   └── connection.js       # PostgreSQL connection setup
├── index.js                # Main Express server
├── package.json
└── README.md
🧑‍💻 Getting Started
Prerequisites
Node.js

PostgreSQL

Installation
Clone the repository:
git clone https://github.com/aryan-0069/MultiUser-Globe-Tracker.git
cd MultiUser-Globe-Tracker
Install dependencies:

bash:
npm install

Set up PostgreSQL database:

Create a database (e.g. family_tracker)

Run this schema:

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
Configure database credentials:

Open db/connection.js

Replace the hardcoded config with your PostgreSQL credentials, for example:

const pool = new Pool({
  user: 'your_pg_user',
  host: 'localhost',
  database: 'family_tracker',
  password: 'your_pg_password',
  port: 5432,
});
Run the app:
bash : node index.js
Open in browser:
Visit http://localhost:3000


# MindFlow

A mood-based productivity web application that helps users manage and complete tasks effectively by adapting task prioritization based on mood, deadlines, and remaining workload. The application focuses on reducing cognitive overload and improving productivity through a clean and responsive user experience.

## Features

* Mood-based task prioritization (Tired, Normal, Productive)
* Dynamic task sorting based on deadlines and work left
* Task creation, update, and completion management
* Work progress tracking using percentage indicators
* Task breakdown through checklists
* File attachment support
* Score and streak tracking system
* Achievement badge system
* Day planner and mini calendar
* Responsive and modern user interface

## Technology Stack

### Frontend

* React.js
* Vite
* Tailwind CSS
* JavaScript (ES6+)

### Backend

* Node.js
* Express.js

### Storage

* Local Storage
* REST APIs

## Project Structure

```text
MindFlow/
├── client/
│   ├── public/
│   └── src/
│       ├── assets/
│       ├── components/
│       ├── hooks/
│       ├── utils/
│       ├── views/
│       ├── App.jsx
│       └── main.jsx
│
├── server/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   └── server.js
│
├── package.json
├── README.md
└── .gitignore
```

## Installation

### Clone the Repository

```bash
git clone https://github.com/<username>/mindflow.git
cd mindflow
```

### Install Frontend Dependencies

```bash
cd client
npm install
npm run dev
```

### Install Backend Dependencies

```bash
cd server
npm install
npm start
```

## Usage

1. Start the frontend and backend servers.
2. Open the application in the browser.
3. Select the current mood.
4. Create tasks and optionally add deadlines, checklists, and attachments.
5. Complete tasks and monitor progress through scores and streaks.

## System Workflow

1. User selects a mood.
2. Tasks are retrieved and prioritized based on:

   * Mood
   * Deadline
   * Remaining workload
3. Users manage and complete tasks.
4. Scores, streaks, and badges are updated automatically.

## Future Enhancements

* AI-based mood detection
* Calendar synchronization
* Push notifications
* Analytics dashboard
* Cloud database integration
* Mobile application support
* Team collaboration features

## React + Vite

This project is built using React and Vite to provide a fast development experience with Hot Module Replacement (HMR) and optimized builds.

### Available React Plugins

* `@vitejs/plugin-react` – Uses Oxc for Fast Refresh
* `@vitejs/plugin-react-swc` – Uses SWC for Fast Refresh

### React Compiler

The React Compiler is not enabled in this project due to its impact on development and build performance. Additional information can be found in the official React documentation.

### ESLint Configuration

For production-grade applications, TypeScript with type-aware linting is recommended. Information on integrating TypeScript and `typescript-eslint` is available in the official Vite React TypeScript template documentation.

## License

This project was developed for educational and academic purposes for a hackathon as a mini project demonstrating mood-aware productivity management using modern web technologies.

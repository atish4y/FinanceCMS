# Finance Content Management System (FCMS)

## Overview

The Finance Content Management System (FCMS) is a full-stack internal web application. It simplifies internal finance document handling by enabling general employees to raise requests and allowing Finance users to upload and manage files securely. The project was developed during a one-month internship and involved end-to-end design and implementation using modern web technologies.

---

## Features

- **Role-Based Dashboard Views**
  - Finance users can view all file requests, upload documents, and track fulfillments.
  - General users can raise requests and view uploaded financial documents.

- **Click-to-Fulfill Mechanism**
  - Finance users can select a request to automatically bind the request ID for upload.
  - Once a file is uploaded, the request is marked as fulfilled in the backend.

- **Session-Based Authentication**
  - Users are authenticated against the `userdata` table.
  - Role detection (Finance or other) is used to route to the appropriate dashboard.

- **Live Document Handling**
  - File uploads by Finance are saved to the backend.
  - Metadata is logged and stored in the MySQL database.

---

## Tech Stack

- **Frontend:** React.js, HTML5, CSS3, JavaScript
- **Backend:** Node.js, Express.js, Multer
- **Database:** MySQL
- **Authentication:** Session-based
- **Design:** Figma
- **Tools:** Postman, VS Code, GitHub

---

## Project Folder Structure

### Frontend (`my-app/`)
```
my-app/
├── public/
├── src/
│   ├── components/
│   │   ├── ControlsSection.js
│   │   ├── FilesTable.js
│   │   ├── Header.js
│   │   └── RequestedFiles.js
│   ├── pages/
│   │   ├── DefaultUserPage.js
│   │   ├── FinanceUserPage.js
│   │   ├── LoginPage.js
│   │   └── ViewReportPage.js
│   ├── data/
│   ├── utils/
│   ├── App.js
│   ├── App.css
│   ├── index.js
│   ├── index.css
│   └── logo.svg
├── package.json
├── package-lock.json
└── README.md
```

### Backend (`PROJ1_BACKEND/`)
```
PROJ1_BACKEND/
├── login-api/
│   ├── uploads/             # Stores uploaded files
│   ├── .env                 # Environment variables
│   ├── db.js                # DB connection logic
│   └── server.js            # Express server entry point
├── node_modules/
├── package.json
└── package-lock.json
```

---

## Database Schema

- **userdata**
  - Stores login credentials and department info
- **requestdata**
  - Tracks employee file requests and their status (0 = pending, 1 = fulfilled)
- **filedata**
  - Logs file uploads with names, descriptions, upload date, and uploader ID

---

## Workflow

1. Users log in via the login page using their credentials from the `userdata` table.
2. Based on department, users are routed to the appropriate dashboard (Finance or General).
3. General users can raise document requests which are saved with a default status of 0.
4. Finance users view all pending requests and can fulfill them by uploading documents.
5. After upload, the corresponding request status is updated to 1, marking it as complete.
6. Uploaded documents are stored on the backend and listed in the dashboards.

---

## UI Enhancements

- Navigation and control sections for seamless interaction.
- Status badges and file filtering for better user experience.


# Bible Reading Progress Tracker (聖經讀經進度追蹤)

A web application for tracking daily Bible reading progress. Users can register or log in using their credentials or Google OAuth and keep a record of their daily Bible reading progress. The app is built using **Flask** for the backend, **Vue.js** for the frontend, and **MySQL** as the database, and it is containerized using **Docker**.

## Features
- User registration and login using credentials.
- Login using Google OAuth.
- Track daily Bible reading progress.
- View historical reading progress.
- Fully containerized with Docker for easy deployment.

## Technologies Used
- **Frontend**: Vue.js
- **Backend**: Flask
- **Database**: MySQL
- **Authentication**: Google OAuth 2.0
- **Containerization**: Docker & Docker Compose

## Project Structure

```
bible-reading-tracker/
├── backend/
│   ├── app.py               # Main Flask application
│   ├── models.py            # SQLAlchemy models for User and Bible reading progress
│   ├── requirements.txt     # Backend dependencies
│   ├── Dockerfile           # Backend Dockerfile
│   └── tests/
│       └── test_app.py      # Unit tests for backend
├── frontend/
│   ├── public/
│   ├── src/
│   │   ├── App.vue          # Vue.js main application component
│   │   ├── main.js          # Vue.js entry point
│   │   └── components/
│   │       └── BibleTracker.vue # Component for Bible reading progress
│   ├── package.json         # Frontend dependencies
│   └── Dockerfile           # Frontend Dockerfile
├── docker-compose.yml       # Docker Compose configuration
└── README.md                # Project overview
```

## Getting Started

### Prerequisites
- Docker
- Docker Compose
- Google Cloud credentials for OAuth (Client ID & Secret)

### Setting up Google OAuth

1. Go to [Google Cloud Console](https://console.cloud.google.com/) and create a new project.
2. Under **APIs & Services**, create OAuth 2.0 credentials.
3. Set the redirect URL as `http://localhost:5000/login/google/authorized`.
4. Save your **Client ID** and **Client Secret**.

### Setting up `.env` file

Create a `.env` file in the `backend/` directory with the following:

```
GOOGLE_CLIENT_ID=your-google-client-id
GOOGLE_CLIENT_SECRET=your-google-client-secret
FLASK_SECRET_KEY=your-flask-secret-key
```

### Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/bible-reading-tracker.git
   cd bible-reading-tracker
   ```

2. Build and start the application using Docker Compose:
   ```bash
   docker-compose up --build
   ```

   This will:
   - Build and start the **MySQL** database.
   - Build and start the **Flask** backend using **Gunicorn** as a WSGI server.
   - Build and serve the **Vue.js** frontend.

### Access the Application

- Backend API: `http://localhost:5000`
- Frontend: `http://localhost:8080`

### Running Tests

You can run backend unit tests using:

```bash
docker-compose exec backend python -m unittest discover -s tests
```

### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

### Additional Sections (optional)

You may want to add sections like **Contributing**, **Troubleshooting**, or **Contact** if needed for your project.


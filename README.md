# 📋 Sky Survey Platform

A modern, dark-themed survey management web application that allows admins to create and manage surveys, and users to respond to them. Built with vanilla HTML, CSS, and JavaScript, communicating with a backend API via XML.

## ✨ Features

### 👨‍💼 Admin Features
- **Survey Management** — Create, edit, soft-delete, restore, and permanently delete surveys
- **Question Builder** — Add, edit, and delete questions to surveys with support for multiple question types:
  - Short Text
  - Long Text
  - Email
  - Single Choice (radio buttons)
  - Multiple Choice (checkboxes)
  - File Upload (with configurable format, max size, and multiple file support)
- **Response Viewer** — View all responses to a survey in a table, with detailed response inspection
- **File Downloads** — Download uploaded files/certificates from responses
- **Share Survey Link** — Copy a direct link to a survey for respondents

### 👤 User Features
- **Respond to Surveys** — Select an active survey and submit responses
- **Direct Survey Links** — Access a survey directly via URL parameter (`?respond=SURVEY_ID`)

### 🎨 UI/UX
- Sleek dark theme design with gradient accents
- Responsive layout (mobile-friendly)
- Animated modals, toasts, and page transitions
- Real-time toast notifications for actions
- Loading spinners and empty states

## 🚀 Getting Started

### Prerequisites
- A modern web browser (Chrome, Firefox, Edge, Safari)
- No server setup required — the app runs entirely on the client side

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/AyiekoGershon/simple-survey-web.git
   cd simple-survey-web
   ```

2. **Open the application**
   - Simply open `login.html` in your web browser, or
   - Serve the files using any static file server:
     ```bash
     # Using Python
     python -m http.server 8000
     
     # Using Node.js (with `npx serve`)
     npx serve .
     ```
   - Navigate to `http://localhost:8000` (or the port provided by your server)

### Demo Credentials

| Role  | Email              | Password   |
|-------|--------------------|------------|
| Admin | admin@survey.com   | admin123   |
| User  | user@example.com   | user123    |

## 🏗️ Project Structure

```
simple-survey-web/
├── index.html          # Main application — survey management & response UI
├── login.html          # Authentication page (role selection & login)
├── README.md           # This file
└── .gitattributes      # Git configuration
```

## 🔧 How It Works

### Authentication
- User credentials are stored in the browser's `localStorage`
- Role-based UI rendering: admins see survey management tools, users only see the respond interface
- Simple logout functionality clears the session

### Backend API
- The app communicates with a REST API at `https://survey-api-luh9.onrender.com/api`
- Data is exchanged in XML format
- All survey, question, and response data is persisted on the backend

### Question Types & Options
- **Short Text** — Single-line text input
- **Long Text** — Multi-line text area
- **Email** — Email-validated input field
- **Single Choice** — Radio button selection (requires predefined options)
- **Multiple Choice** — Checkbox selection (requires predefined options)
- **File Upload** — File input with configurable format, size limit, and multi-upload

### Survey Lifecycle
1. Admin creates a survey (name + description)
2. Admin adds questions with various types
3. Admin shares the survey link with respondents
4. Users select the survey and submit their responses
5. Admin views all responses in the survey detail page
6. Admin can soft-delete surveys (hidden but restorable) or permanently delete them

## 🌐 API Endpoints

The app interacts with the following API endpoints:

| Method   | Endpoint                                   | Description              |
|----------|--------------------------------------------|--------------------------|
| `GET`    | `/surveys`                                 | List all surveys         |
| `POST`   | `/surveys`                                 | Create a new survey      |
| `GET`    | `/surveys/{id}`                            | Get survey details       |
| `PUT`    | `/surveys/{id}`                            | Update a survey          |
| `DELETE` | `/surveys/{id}`                            | Delete a survey          |
| `GET`    | `/surveys/{id}/questions`                  | List survey questions    |
| `POST`   | `/surveys/{id}/questions`                  | Add question to survey   |
| `GET`    | `/surveys/{id}/responses`                  | List survey responses    |
| `POST`   | `/surveys/{id}/responses`                  | Submit a response        |
| `PUT`    | `/questions/{id}`                          | Update a question        |
| `DELETE` | `/questions/{id}`                          | Delete a question        |
| `GET`    | `/certificates/{id}`                       | Download uploaded file   |

## 🎨 Design Highlights

- **Dark theme** with carefully chosen color variables for consistency
- **Glassmorphism** effects (backdrop blur on header and toasts)
- **Animated elements** — smooth page transitions, modal slide-ups, toast slide-ins, hover effects
- **Responsive grid layout** for survey cards that adapts to screen size
- **Gradient text** accents on headings and statistics
- **Custom scrollbar** styling

## 🤝 Contributing

Contributions are welcome! Feel free to submit issues or pull requests.

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## 📝 License

This project is open source. Feel free to use and modify it as needed.

---

Built with ❤️ using vanilla HTML, CSS, and JavaScript.

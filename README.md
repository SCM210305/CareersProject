# CareerVerse AI — Full-Stack AI Career Platform

CareerVerse AI is a full-stack career development platform designed to help users analyze resumes, evaluate ATS compatibility, match job descriptions, improve resume content, and prepare for interviews using AI-powered services.

## Project Structure
```text
careerverse-ai/
│
├── frontend/                                  # React + Tailwind
│   ├── public/
│   ├── src/
│   │   ├── api/
│   │   │   └── axios.js                       # Axios instance + JWT interceptor
│   │   ├── components/
│   │   │   ├── ProtectedRoute.jsx
│   │   │   ├── Navbar.jsx
│   │   │   ├── ResumeUploadCard.jsx
│   │   │   ├── AtsScoreBreakdown.jsx
│   │   │   ├── JdMatchCard.jsx
│   │   │   ├── TimelineFeed.jsx
│   │   │   └── InterviewChat.jsx
│   │   ├── pages/
│   │   │   ├── Login.jsx
│   │   │   ├── Register.jsx
│   │   │   ├── Dashboard.jsx
│   │   │   ├── ResumePage.jsx
│   │   │   ├── JdMatcherPage.jsx
│   │   │   ├── RewriterPage.jsx
│   │   │   ├── CoachPage.jsx
│   │   │   ├── InterviewPage.jsx
│   │   │   └── TimelinePage.jsx
│   │   ├── context/
│   │   │   └── AuthContext.jsx
│   │   ├── App.jsx
│   │   └── main.jsx
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── backend/                                   # Java + Spring Boot
│   ├── src/main/java/com/careerverse/
│   │   ├── controller/
│   │   │   ├── AuthController.java
│   │   │   ├── ResumeController.java
│   │   │   ├── AtsScoreController.java
│   │   │   ├── JobDescriptionController.java
│   │   │   ├── JdMatchController.java
│   │   │   ├── RewriteController.java
│   │   │   ├── CoachController.java
│   │   │   ├── InterviewController.java
│   │   │   └── TimelineController.java
│   │   ├── service/
│   │   │   ├── AuthService.java
│   │   │   ├── ResumeService.java
│   │   │   ├── AtsScoreService.java
│   │   │   ├── JdMatchService.java
│   │   │   ├── RewriteService.java
│   │   │   ├── CoachService.java
│   │   │   ├── InterviewService.java
│   │   │   ├── TimelineService.java
│   │   │   └── AiServiceClient.java
│   │   ├── repository/
│   │   │   ├── UserRepository.java
│   │   │   ├── ResumeRepository.java
│   │   │   ├── AtsScoreRepository.java
│   │   │   ├── JobDescriptionRepository.java
│   │   │   ├── JdMatchRepository.java
│   │   │   ├── RewriteSessionRepository.java
│   │   │   ├── InterviewRepository.java
│   │   │   ├── InterviewScoreRepository.java
│   │   │   ├── CareerTimelineRepository.java
│   │   │   └── CoachSuggestionRepository.java
│   │   ├── model/                              # JPA entities
│   │   │   ├── Role.java
│   │   │   ├── User.java
│   │   │   ├── Resume.java
│   │   │   ├── AtsScore.java
│   │   │   ├── JobDescription.java
│   │   │   ├── JdMatch.java
│   │   │   ├── RewriteSession.java
│   │   │   ├── Interview.java
│   │   │   ├── InterviewScore.java
│   │   │   ├── CareerTimeline.java
│   │   │   └── CoachSuggestion.java
│   │   ├── security/
│   │   │   ├── JwtUtil.java
│   │   │   └── JwtAuthFilter.java
│   │   ├── dto/
│   │   │   ├── AuthDtos.java
│   │   │   ├── ResumeDtos.java
│   │   │   ├── AtsScoreDtos.java
│   │   │   ├── JdMatchDtos.java
│   │   │   ├── RewriteDtos.java
│   │   │   ├── InterviewDtos.java
│   │   │   └── TimelineDtos.java
│   │   └── config/
│   │       └── SecurityConfig.java
│   ├── src/main/resources/
│   │   └── application.properties
│   └── pom.xml
│
├── ai-service/                                 # Python + FastAPI
│   ├── app/
│   │   ├── routers/
│   │   │   ├── parse_resume.py
│   │   │   ├── ats_score.py
│   │   │   ├── match_jd.py
│   │   │   ├── rewrite.py
│   │   │   ├── interview.py
│   │   │   └── coach.py
│   │   ├── services/
│   │   │   ├── openai_client.py
│   │   │   ├── prompts.py
│   │   │   └── ...
│   │   ├── models/
│   │   │   └── schemas.py
│   │   └── main.py
│   ├── requirements.txt
│   └── Dockerfile
│
├── database/
│   └── schema.sql
│
├── docs/
│   ├── api-contract.md
│   ├── db-schema.md
│   └── feature-ownership.md
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── .env.example
├── .gitignore
└── README.md
```

## Technology Stack

- **Frontend:** React.js, Tailwind CSS, Vite
- **Backend:** Java, Spring Boot, Spring Security
- **AI Service:** Python, FastAPI, OpenAI API
- **Database:** MySQL
- **Authentication:** JWT
- **DevOps:** GitHub Actions, Docker, AWS (if configured)

## Core Features

- User registration and authentication
- Resume upload and analysis
- ATS score evaluation and breakdown
- Job description matching
- AI-powered resume rewriting
- Personalized career coaching
- Interview preparation
- Career timeline tracking

## Getting Started

Refer to the frontend, backend, and AI service directories for component-specific setup instructions.

Configure the required environment variables using `.env.example`. Do not commit API keys, passwords, or other secrets.

## Project Status

Under development.

## Future Enhancements

- Improved resume analysis and job recommendations
- Expanded interview assessment features
- Automated testing and deployment

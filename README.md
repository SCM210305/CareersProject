# CareersProject
careerverse-ai/
│
├── frontend/                                  # React + Tailwind
│   ├── public/
│   ├── src/
│   │   ├── api/
│   │   │   └── axios.js                       # ✅ built — axios instance + JWT interceptor
│   │   ├── components/
│   │   │   ├── ProtectedRoute.jsx              # ✅ built
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
│   │   │   └── AuthContext.jsx                 # ✅ built
│   │   ├── App.jsx                             # ✅ built
│   │   └── main.jsx
│   ├── package.json
│   ├── vite.config.js
│   └── tailwind.config.js
│
├── backend/                                   # Java + Spring Boot
│   ├── src/main/java/com/careerverse/
│   │   ├── controller/
│   │   │   ├── AuthController.java             # ✅ built
│   │   │   ├── ResumeController.java
│   │   │   ├── AtsScoreController.java
│   │   │   ├── JobDescriptionController.java
│   │   │   ├── JdMatchController.java
│   │   │   ├── RewriteController.java
│   │   │   ├── CoachController.java
│   │   │   ├── InterviewController.java
│   │   │   └── TimelineController.java
│   │   ├── service/
│   │   │   ├── AuthService.java                # ✅ built
│   │   │   ├── ResumeService.java
│   │   │   ├── AtsScoreService.java
│   │   │   ├── JdMatchService.java
│   │   │   ├── RewriteService.java
│   │   │   ├── CoachService.java
│   │   │   ├── InterviewService.java
│   │   │   ├── TimelineService.java            # shared writer used by every other service
│   │   │   └── AiServiceClient.java            # REST client → ai-service
│   │   ├── repository/
│   │   │   ├── UserRepository.java             # ✅ built
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
│   │   │   ├── Role.java                       # ✅ built
│   │   │   ├── User.java                       # ✅ built
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
│   │   │   ├── JwtUtil.java                    # ✅ built
│   │   │   └── JwtAuthFilter.java              # ✅ built
│   │   ├── dto/
│   │   │   ├── AuthDtos.java                   # ✅ built
│   │   │   ├── ResumeDtos.java
│   │   │   ├── AtsScoreDtos.java
│   │   │   ├── JdMatchDtos.java
│   │   │   ├── RewriteDtos.java
│   │   │   ├── InterviewDtos.java
│   │   │   └── TimelineDtos.java
│   │   └── config/
│   │       └── SecurityConfig.java             # ✅ built
│   ├── src/main/resources/
│   │   └── application.properties              # ✅ built
│   └── pom.xml                                 # ✅ built
│
├── ai-service/                                 # Python + FastAPI
│   ├── app/
│   │   ├── routers/
│   │   │   ├── parse_resume.py                 # ✅ built (template)
│   │   │   ├── ats_score.py
│   │   │   ├── match_jd.py
│   │   │   ├── rewrite.py
│   │   │   ├── interview.py
│   │   │   └── coach.py
│   │   ├── services/
│   │   │   ├── openai_client.py                # ✅ built
│   │   │   ├── prompts.py                      # prompt templates, kept out of routers
│   │   │   └── ...
│   │   ├── models/
│   │   │   └── schemas.py                      # shared Pydantic request/response models
│   │   └── main.py                             # ✅ built
│   ├── requirements.txt
│   └── Dockerfile                              # optional, for EC2 deploy
│
├── database/
│   └── schema.sql                              # ✅ built
│
├── docs/
│   ├── api-contract.md                         # ✅ built
│   ├── db-schema.md                            # plain-English notes on schema.sql
│   └── feature-ownership.md                    # who owns which feature vertical
│
├── .github/
│   └── workflows/
│       └── ci.yml                              # ✅ built
│
├── .env.example                                # ✅ built
├── .gitignore
└── README.md
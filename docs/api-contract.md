# CareerVerse AI — API Contract

Base URL (backend): `/api/v1`
Base URL (ai-service, internal only): `/ai/v1`

All backend endpoints (except auth) require `Authorization: Bearer <JWT>`.

## Response envelope

Success:
```json
{ "success": true, "data": { }, "message": "" }
```
Error:
```json
{ "success": false, "error": { "code": "STRING_CODE", "message": "human readable" } }
```

---

## Auth

### POST /api/v1/auth/register
Body: `{ "name": "", "email": "", "password": "" }`
Returns: `{ "userId": 1, "token": "" }`

### POST /api/v1/auth/login
Body: `{ "email": "", "password": "" }`
Returns: `{ "token": "", "role": "STUDENT" }`

---

## Resume

### POST /api/v1/resumes
Multipart file upload → stores in S3, calls ai-service `/parse-resume`, saves `parsed_json`.
Returns: `{ "resumeId": 1, "parsedData": { } }`

### GET /api/v1/resumes/{id}
Returns full parsed resume + version history.

---

## ATS Score

### POST /api/v1/resumes/{id}/ats-score
Calls ai-service `/ats-score`, stores result.
Returns: `{ "overallScore": 78, "breakdown": { "keywords": 20, "formatting": 15, "quantifiedAchievements": 10, ... } }`

---

## Job Description Matcher

### POST /api/v1/job-descriptions
Body: `{ "rawText": "" }`
Returns: `{ "jdId": 1 }`

### POST /api/v1/resumes/{resumeId}/match/{jdId}
Calls ai-service `/match-jd`.
Returns: `{ "matchPercent": 82.5, "missingSkills": [], "weakAreas": [], "suggestedTopics": [] }`

---

## Resume Rewriter

### POST /api/v1/resumes/{id}/rewrite/start
Returns clarifying questions: `{ "sessionId": 1, "questions": [ { "id": "q1", "text": "" } ] }`

### POST /api/v1/rewrite-sessions/{sessionId}/answer
Body: `{ "answers": [ { "questionId": "q1", "answer": "" } ] }`
Returns: `{ "updatedResume": { } }`

---

## Career Coach

### GET /api/v1/coach/suggestions
Returns current suggestions: `{ "suggestions": [ { "id": 1, "text": "", "status": "PENDING" } ] }`

### PATCH /api/v1/coach/suggestions/{id}
Body: `{ "status": "DISMISSED" | "DONE" }`

---

## Mock Interview

### POST /api/v1/interviews
Body: `{ "company": "", "role": "", "roundType": "TECHNICAL" | "BEHAVIORAL" }`
Returns: `{ "interviewId": 1, "firstQuestion": "" }`

### POST /api/v1/interviews/{id}/answer
Body: `{ "answer": "" }`
Returns: `{ "nextQuestion": "" }` or `{ "complete": true }`

### GET /api/v1/interviews/{id}/feedback
Returns: `{ "technical": 8, "communication": 7, "structure": 9, "confidence": 6, "feedbackText": "", "studyPlan": [] }`

---

## Career Timeline

### GET /api/v1/timeline
Returns: `{ "events": [ { "eventType": "", "summary": "", "createdAt": "" } ] }` (paginated, newest first)

---

## Internal AI-service endpoints (called by backend only, not exposed to frontend)

- `POST /ai/v1/parse-resume`
- `POST /ai/v1/ats-score`
- `POST /ai/v1/match-jd`
- `POST /ai/v1/rewrite`
- `POST /ai/v1/interview/next-question`
- `POST /ai/v1/interview/feedback`
- `POST /ai/v1/coach`

## Error codes

| Code | Meaning |
|---|---|
| `AUTH_INVALID` | Bad credentials |
| `AUTH_EXPIRED` | Token expired |
| `NOT_FOUND` | Resource doesn't exist |
| `VALIDATION_ERROR` | Bad request body |
| `AI_SERVICE_ERROR` | ai-service call failed |
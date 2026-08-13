# 🌍 AI-Community-Problem-Solver
### 📌 Project Overview
AI Community problem solver is an AI-Powered web application designed to improve how citizens report community issues and how local authorities manage and resolve them.

Citizens can report an issues by updating an image, adding short discription, and sharing the location.The AI analyzes the image, identifies the issue category, assigns a priority level, confidence score and appropriate authority. Authorities can assign field officers, track progress, and update the report until it is resolved.

The main goal of the system is to make community issue reporting faster, more accurate, and transparent for both citizens and authorities.

---
### 🎯 Problem Segment / Theme

Project Theme
- Improving Community issue Reporting and Resolution Using Artificial Intelligence

Problem Segment
- Many community issues remains unresolved because the reporting process is slow and inefficient.

Common community issues include:

- Illegal garbage dumping
- Damaged roads
- Broken streetlights
- Water leaks
- Fallen trees
- Drainage problems
- Public infrastructure damage

Current complaint systems often have several limitations:
- Slow response from authorities.
- Poor communication between citizens and authorities.
- Manual issue categorization.
- No automatic priority assignment.
- No proper way for citizens to track report progress.
- Difficulty identifying the correct authority responsible for the issue.
This project aims to solve these problems using Artificial Intelligence.
---
### 📊 Market Research
1. Existing Government Complaint Systems

Examples:
- Municipal Council Complaint Systems
- Local Government Complaint Portals

Limitations:
- Manual complaint submission
- Limited tracking
- Slow responses
- No AI support

2. Mobile Complaint Applications

Features:
- Issue reporting
- GPS location sharing
- Complaint tracking
  
Limitations:
- Users manually select issue categories
- No automatic priority detection
- Limited communication with authorities

3. International Platforms

Examples
- FixMyStreet
- SeeClickFix

Features:
- Public issue reporting
- Location-based reports
- Communication with authorities

Limitations:
- Mainly focused on reporting
- Limited AI automation
- Limited workflow management

| Problem              | Current Situation   |
| -------------------- | ------------------- |
| Issue identification | Manual              |
| Priority assignment  | Manual              |
| Authority selection  | User decides        |
| Progress tracking    | Limited             |
| Communication        | Slow                |
| Emergency response   | No automatic alerts |

---
### 📌 Top 5 Problems (MoSCoW Prioritization)
| Problem                     | Priority    | Reason                                  |
| --------------------------- | ----------- | --------------------------------------- |
| Difficult issue reporting   | Must Have   | Citizens need an easy reporting process |
| Slow authority response     | Must Have   | Delays issue resolution                 |
| No report tracking          | Must Have   | Citizens need transparency              |
| Wrong authority assignment  | Should Have | Causes unnecessary delays               |
| Manual issue classification | Should Have | Increases workload                      |

---
### 🗺 Customer Journey Map

| Stage          | User Action                 | Problem                      | Improvement             |
| -------------- | --------------------------- | ---------------------------- | ----------------------- |
| Identify Issue | Notices a community problem | Doesn't know where to report | Easy reporting platform |
| Report Issue   | Submits report              | Long forms                   | Image-based reporting   |
| Waiting        | Waits for response          | No updates                   | Real-time tracking      |
| Resolution     | Issue resolved              | No proof                     | Resolution image upload |
| Feedback       | Reviews result              | Poor communication           | Notifications           |
---
### 🚀 Final Solution

The AI Community Problem Solver is an intelligent web application that helps citizens report community issues quickly and easily.

Benefits
- Easy issue reporting
- Automatic issue detection
- AI-based prioritization
- Correct authority routing
- Faster response time
- Transparent tracking
- Better communication

---
### 🛡 Stress Testing

| Challenge               | Risk               | Solution                  |
| ----------------------- | ------------------ | ------------------------- |
| Wrong AI detection      | Incorrect category | Authority verification    |
| Fake reports            | System misuse      | User authentication       |
| Large number of reports | Performance issues | Cloud scalability         |
| Poor image quality      | AI errors          | Request better images     |
| Authority delays        | Slow resolution    | Escalation notifications  |
| GPS errors              | Wrong location     | Manual location selection |

---
### 🌟 Future Improvements

- AI chatbot for citizen support
- Predictive analysis for recurring issues
- Emergency alert detection
- Multi-language support
- Mobile application for Android and iOS
- Integration with IoT devices and smart city systems
- Analytics dashboard for authorities
- AI-powered report recommendations

---
### 🎯 The Core Gap
The main gap is the disconnect between how fast citizens report problems and how slow authorities process and fix them.

Right now, traditional complaint systems rely heavily on manual human effort at every step. This project bridges the gap by replacing slow manual steps with automated AI intelligence and real-time communication.

1. The Automation Gap (Manual vs. AI Processing)
   
Existing Systems: 

When a citizen files a complaint, a human worker has to read it, figure out what the problem is (garbage,fallen tree), determine how urgent it is, and guess which department should handle it. This creates a huge backlog.

The Gap Solved: 

The system uses AI image analysis to automatically identify the issue, assign a priority level (High/Medium/Low), and route it to the correct authority instantly upon submission.

2. The Communication & Routing Gap (The "Wrong Department" Problem)
   
Existing Systems: 

Citizens often don't know who is responsible for what (e.g., Is this leak a city council problem or a water board problem?). Complaints often sit in the wrong inbox for weeks.

The Gap Solved: 

The platform acts as a centralized bridge. It automatically maps the issue to the correct local authority and triggers an end-to-end workflow—notifying field officers immediately via SMS and push notifications with exact GPS locations.

3. The Transparency & Tracking Gap (The "Black Hole" Effect)

Existing Systems: 

Once a citizen submits a complaint, they rarely hear back. They have no idea if anyone is working on it or if it was ignored, leading to frustration and distrust.

The Gap Solved: 

It introduces end-to-end real-time tracking. Citizens get status updates from submission to resolution, including visual proof (the field officer must upload a completion photo before closing the ticket).

---
### 🏗️ High-Level Architecture

<img width="1382" height="808" alt="High_Level_Architecture" src="https://github.com/user-attachments/assets/4d05ad93-25e4-4355-bd19-f793f7351f92" />

---
### 📱 Low-Fidelity Wireframes & 🎨 High-Fidelity App Design

https://www.figma.com/make/WFoXSbF7GLd2JWiRZk8tBf/Low-Fidelity-Wireframes-for-App?t=iNF0ueVJ7SLTmrEA-20&fullscreen=1

---
### Civic Link — Backend API

The backend manages users and access permissions for the following roles:

| Role        | Description                                 |
| ----------- | ------------------------------------------- |
| `CITIZEN`   | Reports and tracks community issues         |
| `ADMIN`     | Manages authorities and officers            |
| `AUTHORITY` | Manages issues assigned to the organization |
| `OFFICER`   | Handles field-level issue resolution        |

---

### ✨ Key Features

### Authentication

* Citizen registration
* Login for all user roles
* JWT-based authentication
* Current-user information
* Logout
* Password change
* Invitation-based onboarding
* Temporary passwords for newly created authority/officer accounts

### Role-Based Access Control

Protected endpoints enforce user roles.

For example:

* Citizens cannot access administrator endpoints
* Only administrators can create authorities
* Only administrators can create officers
* Authenticated users can manage their own passwords and sessions

### Authority Management

Administrators can:

* Create authorities
* View registered authorities
* View authority details
* Associate officers with authorities

### Officer Management

Administrators can:

* Create officers
* Assign officers to authorities
* View officers
* Reset officer temporary passwords

### Invitation System

Authority and officer accounts can be created with an invitation workflow:

```text
Admin creates account
        ↓
Temporary password + invitation URL
        ↓
User opens invitation
        ↓
User sets a new password
        ↓
User logs in
```

---

### 🛠️ Tech Stack

| Technology              | Purpose                              |
| ----------------------- | ------------------------------------ |
| Node.js                 | Backend runtime                      |
| Express.js              | REST API framework                   |
| Supabase                | Authentication and database services |
| PostgreSQL              | Relational database                  |
| JavaScript / TypeScript | Backend development                  |
| REST API                | Frontend/backend communication       |

---

### ⚙️ Getting Started

### 1. Clone the repository

```bash
git clone <your-backend-repository-url>
cd Civic_AI_Backend
```

### 2. Install dependencies

```bash
npm install
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
SUPABASE_URL=your_supabase_project_url
SUPABASE_ANON_KEY=your_supabase_anon_key
SUPABASE_SERVICE_ROLE_KEY=your_supabase_service_role_key

DATABASE_URL=your_postgresql_connection_string

FRONTEND_URL=http://localhost:5173
```

### Environment Variables

| Variable                    | Description                                     | Required |
| --------------------------- | ----------------------------------------------- | -------- |
| `SUPABASE_URL`              | Supabase project URL                            | Yes      |
| `SUPABASE_ANON_KEY`         | Supabase public authentication key              | Yes      |
| `SUPABASE_SERVICE_ROLE_KEY` | Server-side Supabase service key                | Yes      |
| `DATABASE_URL`              | PostgreSQL database connection                  | Yes      |
| `FRONTEND_URL`              | Frontend URL used for CORS and invitation links | Yes      |

> ⚠️ **Security:** Never commit `.env` or expose `SUPABASE_SERVICE_ROLE_KEY` in frontend code.

---

### ▶️ Running the Backend

Start the development server:

```bash
npm run dev
```

The API will be available at:

```text
http://localhost:5000
```

---

### ❤️ Health Check

Verify that the API is running:

```http
GET /api/health
```

Example response:

```json
{
  "success": true,
  "message": "Civic Link API is running"
}
```

---

### 🔐 Authentication

Protected endpoints require a Bearer token:

```http
Authorization: Bearer <access_token>
```

The access token is returned after login:

```text
data.session.access_token
```

Example:

```http
Authorization: Bearer eyJhbGciOi...
```

---

### 📡 API Reference

**Base URL**

```text
http://localhost:5000
```

### Authentication Endpoints

| Method | Endpoint                    | Auth | Role      |
| ------ | --------------------------- | ---- | --------- |
| `POST` | `/api/auth/register`        | No   | Citizen   |
| `POST` | `/api/auth/login`           | No   | All roles |
| `GET`  | `/api/auth/invite/:token`   | No   | Public    |
| `POST` | `/api/auth/accept-invite`   | No   | Public    |
| `GET`  | `/api/auth/me`              | Yes  | Any user  |
| `POST` | `/api/auth/logout`          | Yes  | Any user  |
| `POST` | `/api/auth/change-password` | Yes  | Any user  |

### Administration Endpoints

| Method | Endpoint                                        | Auth | Role    |
| ------ | ----------------------------------------------- | ---- | ------- |
| `GET`  | `/api/admin/authorities`                        | Yes  | `ADMIN` |
| `POST` | `/api/admin/authorities`                        | Yes  | `ADMIN` |
| `GET`  | `/api/admin/officers`                           | Yes  | `ADMIN` |
| `POST` | `/api/admin/officers`                           | Yes  | `ADMIN` |
| `POST` | `/api/admin/officers/:officerId/reset-password` | Yes  | `ADMIN` |

### Development

| Method | Endpoint             | Auth |
| ------ | -------------------- | ---- |
| `GET`  | `/api/test/supabase` | No   |

> `/api/test/supabase` is intended only for development/testing.

---

### 📝 Request Examples

### Register Citizen

```http
POST /api/auth/register
Content-Type: application/json
```

```json
{
  "fullName": "Jane Citizen",
  "email": "jane.citizen@gmail.com",
  "phone": "5551234567",
  "password": "password123",
  "confirmPassword": "password123"
}
```

---

### Login

```http
POST /api/auth/login
Content-Type: application/json
```

```json
{
  "email": "admin@civiclink.gov",
  "password": "YourSecurePass123!"
}
```

Example response:

```json
{
  "success": true,
  "message": "Login successful",
  "data": {
    "user": {
      "id": "uuid-here",
      "fullName": "System Admin",
      "email": "admin@civiclink.gov",
      "role": "ADMIN",
      "isPasswordSet": true,
      "invitationStatus": "ACCEPTED"
    },
    "session": {
      "access_token": "eyJhbG...",
      "refresh_token": "...",
      "expires_in": 3600
    },
    "requiresPasswordChange": false
  }
}
```

Save:

```text
data.session.access_token
```

for subsequent protected requests.

---

### 👤 Current User

```http
GET /api/auth/me
Authorization: Bearer <access_token>
```

This endpoint returns the authenticated user's profile, role, authority information, and officer information where applicable.

---

### 🏢 Create Authority

Only administrators can create authorities.

```http
POST /api/admin/authorities
Authorization: Bearer <admin_access_token>
Content-Type: application/json
```

```json
{
  "name": "Public Works Dept.",
  "email": "works@gov.ng",
  "phone": "5559876543",
  "address": "123 Main Street",
  "coverage": "Metro North",
  "district": "Central District",
  "description": "Handles road and infrastructure reports"
}
```

Example response:

```json
{
  "success": true,
  "message": "Authority created successfully",
  "data": {
    "authority": {
      "id": "authority-uuid",
      "name": "Public Works Dept."
    },
    "tempPassword": "Xk9#mP2vLq4@",
    "inviteUrl": "http://localhost:5173/accept-invite?token=abc123"
  }
}
```

---

### 👮 Create Officer

```http
POST /api/admin/officers
Authorization: Bearer <admin_access_token>
Content-Type: application/json
```

```json
{
  "firstName": "Samuel",
  "lastName": "Johnson",
  "email": "samuel.johnson@gov.ng",
  "phone": "5551112233",
  "position": "Field Officer",
  "department": "Road Maintenance",
  "authorityId": "authority-uuid"
}
```

---

### 🔑 Accept Invitation

```http
POST /api/auth/accept-invite
Content-Type: application/json
```

```json
{
  "token": "invitation-token",
  "password": "MyNewSecure123!",
  "confirmPassword": "MyNewSecure123!"
}
```

---

### 🔄 Change Password

```http
POST /api/auth/change-password
Authorization: Bearer <access_token>
Content-Type: application/json
```

```json
{
  "currentPassword": "TemporaryPass123!",
  "newPassword": "MyNewSecure456!",
  "confirmPassword": "MyNewSecure456!"
}
```

---

### 🔁 Reset Officer Password

Administrators can reset an officer's password.

```http
POST /api/admin/officers/:officerId/reset-password
Authorization: Bearer <admin_access_token>
```

Example:

```http
POST /api/admin/officers/officer-uuid/reset-password
```

---

### 📦 Standard Response Format

### Success

```json
{
  "success": true,
  "message": "Optional message",
  "data": {}
}
```

### Error

```json
{
  "success": false,
  "message": "Error description"
}
```

### Validation Error

```json
{
  "success": false,
  "message": "Validation failed",
  "errors": [
    {
      "path": ["email"],
      "message": "Please provide a valid email address"
    }
  ]
}
```

---

### 🚦 HTTP Status Codes

| Status | Meaning                                      |
| ------ | -------------------------------------------- |
| `200`  | Request successful                           |
| `201`  | Resource created                             |
| `400`  | Validation error                             |
| `401`  | Missing/invalid token or invalid credentials |
| `403`  | Insufficient permissions                     |
| `500`  | Internal server error                        |

---

### 🧪 Testing the API

Civic Link can be tested using:

* Thunder Client
* VS Code REST Client
* Postman
* cURL
* PowerShell

### Recommended Testing Flow

```text
Health Check
     ↓
Admin Login
     ↓
Create Authority
     ↓
Create Officer
     ↓
Validate Invitation
     ↓
Accept Invitation
     ↓
Officer/Authority Login
     ↓
Change Password
     ↓
Get Current User
```

---

### 🧰 REST Client Example

Create:

```text
civic-link-api.http
```

Then add:

```http
@baseUrl = http://localhost:5000
@token = paste_access_token_here

### Health Check
GET {{baseUrl}}/api/health

### Login
POST {{baseUrl}}/api/auth/login
Content-Type: application/json

{
  "email": "admin@civiclink.gov",
  "password": "YourSecurePass123!"
}

### Current User
GET {{baseUrl}}/api/auth/me
Authorization: Bearer {{token}}

### List Authorities
GET {{baseUrl}}/api/admin/authorities
Authorization: Bearer {{token}}
```

---

### 📮 Postman

A Postman collection is included in:

```text
postman/Civic_Link_API.postman_collection.json
```

Import the collection into Postman and run the **Login** request first.

The returned access token can then be used for protected endpoints.

---

### 🔒 Security Considerations

* Keep environment variables outside source control.
* Never expose the Supabase service-role key to the frontend.
* Use HTTPS in production.
* Use strong passwords.
* Protect admin-only routes with role-based authorization.
* Do not store access tokens in insecure locations.
* Never log passwords or temporary credentials.
* Restrict CORS to trusted frontend origins in production.

---

### 🌍 Production Configuration

For production deployment, update:

```env
FRONTEND_URL=https://your-frontend-domain.com
```

and configure the backend to use production Supabase/PostgreSQL credentials.

The production environment should also use:

```text
HTTPS
Secure environment variables
Restricted CORS
Production database
Production Supabase project
```

---

### 🔗 Frontend Integration

The frontend can communicate with the backend using the base URL:

```javascript
const API_BASE_URL = "http://localhost:5000";
```

Example request:

```javascript
const response = await fetch(
  `${API_BASE_URL}/api/auth/me`,
  {
    headers: {
      Authorization: `Bearer ${accessToken}`,
      "Content-Type": "application/json"
    }
  }
);

const data = await response.json();
```

---

### 👥 User Roles

```text
                    ┌─────────────┐
                    │    ADMIN    │
                    └──────┬──────┘
                           │
             ┌─────────────┴─────────────┐
             ▼                           ▼
      ┌──────────────┐           ┌──────────────┐
      │  AUTHORITY   │           │   OFFICER    │
      └──────────────┘           └──────────────┘

                    ┌──────────────┐
                    │   CITIZEN    │
                    └──────────────┘
```

### Permissions

| Feature                | Citizen | Admin | Authority | Officer |
| ---------------------- | :-----: | :---: | :-------: | :-----: |
| Register               |    ✅    |   ❌   |     ❌     |    ❌    |
| Login                  |    ✅    |   ✅   |     ✅     |    ✅    |
| View own profile       |    ✅    |   ✅   |     ✅     |    ✅    |
| Change password        |    ✅    |   ✅   |     ✅     |    ✅    |
| Create authorities     |    ❌    |   ✅   |     ❌     |    ❌    |
| View authorities       |    ❌    |   ✅   |     ❌     |    ❌    |
| Create officers        |    ❌    |   ✅   |     ❌     |    ❌    |
| Reset officer password |    ❌    |   ✅   |     ❌     |    ❌    |

---

### 📊 API Summary

```text
Health
 └── GET /api/health

Authentication
 ├── POST /api/auth/register
 ├── POST /api/auth/login
 ├── GET  /api/auth/invite/:token
 ├── POST /api/auth/accept-invite
 ├── GET  /api/auth/me
 ├── POST /api/auth/logout
 └── POST /api/auth/change-password

Administration
 ├── GET  /api/admin/authorities
 ├── POST /api/admin/authorities
 ├── GET  /api/admin/officers
 ├── POST /api/admin/officers
 └── POST /api/admin/officers/:officerId/reset-password

Development
 └── GET /api/test/supabase
```

---

### 🧑‍💻 Development

Recommended development workflow:

```bash
# Create a feature branch
git checkout -b feature/your-feature

# Make changes
git add .

# Commit
git commit -m "feat: implement your feature"

# Push
git push -u origin feature/your-feature
```

Create a pull request and merge the completed feature into the development branch after review.

---

### 🤝 Contributing

1. Create a feature branch.
2. Implement the required changes.
3. Test the API locally.
4. Commit using a meaningful commit message.
5. Push the branch.
6. Create a pull request.
7. Merge after review and successful testing.

---




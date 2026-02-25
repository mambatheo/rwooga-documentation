The system is divided into two fully decoupled deployments communicating via a JSON REST API.
SYSTEM OVERVIEW DIAGRAM
[User Browser]
|
v
[Vercel Edge Network]  <-- React 19 + Vite SPA (Frontend)
|  (HTTPS API calls to /api/*)
v
[Koyeb Cloud Host]  <-- Django REST Framework API (Backend)
|
+---------+-------------+-------------+
v         v             v             v
[PostgreSQL] [Cloudinary] [Paypack API] [SMTP Server]
(Database)  (Media CDN)  (Payments)   (Email)

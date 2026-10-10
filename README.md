# Project 1: Personal Portfolio Website
Stack: HTML, CSS, JavaScript, Express, MongoDB, optional Nodemailer SMTP.

## Windows run steps
1. Install Node.js LTS and MongoDB Community Server, or use MongoDB Atlas.
2. Extract ZIP and open `Personal-Portfolio` in VS Code.
3. Open Terminal in that folder; run `npm install`.
4. Copy `.env.example` to `.env` and set `MONGODB_URI`. Local default: `mongodb://127.0.0.1:27017/portfolio_db`.
5. Start MongoDB, then run `npm start`. Open http://localhost:5000.

## API routes
- GET `/api/health`
- GET `/api/portfolio` gets dynamic profile, skills and projects.
- PUT `/api/portfolio` updates profile JSON. This demo endpoint must be protected by admin authentication before public deployment.
- POST `/api/contact` validates and saves messages; SMTP email is optional.

Example PUT JSON (use Postman, URL `http://localhost:5000/api/portfolio`, method PUT, Content-Type application/json):
```json
{"name":"Mayur Kharat","title":"BCA Student | Full Stack Developer","summary":"I create responsive web apps.","location":"Maharashtra, India","email":"you@example.com","skills":["HTML","CSS","JavaScript","Node.js","Express.js","MongoDB"],"projects":[{"title":"Smart Village Management System","description":"BCA final year project","link":"https://github.com/your-name/repo"}]}
```
To enable email, fill SMTP environment variables in `.env`; Gmail users should use an App Password. Never publish `.env` or credentials. Before public production, protect the update route, enable HTTPS and add monitoring/rate limiting. Replace sample content with your own.

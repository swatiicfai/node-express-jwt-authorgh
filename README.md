# Node.js Express JWT Authentication Assignment

## Features
- Register new users with password hashing (bcrypt)
- Login with password verification (bcrypt.compare)
- JWT authentication for protected routes
- In-memory user storage (no database)

## Routes
- `POST /register` — Register new user
- `POST /login` — Login user and receive JWT
- `GET /profile` — Protected route, requires JWT

## How to Run

1. **Install dependencies:**
   ```bash
   npm install
   ```
2. **Start the server:**
   ```bash
   npm start
   ```
3. **Test the API:**
   - Use Postman, curl, or similar tools.

### Example Requests

#### Register
```bash
curl -X POST http://localhost:3000/register \
  -H 'Content-Type: application/json' \
  -d '{"username":"alice","password":"password123"}'
```

#### Login
```bash
curl -X POST http://localhost:3000/login \
  -H 'Content-Type: application/json' \
  -d '{"username":"alice","password":"password123"}'
```
Response will include a `token`.

#### Access Protected Profile
```bash
curl http://localhost:3000/profile \
  -H 'Authorization: Bearer <token>'
```

Replace `<token>` with the JWT received from login.

---

**Note:** This is a demo assignment. For production, use environment variables for secrets and a real database for user storage.
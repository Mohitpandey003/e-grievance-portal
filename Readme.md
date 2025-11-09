# E-Grievance Portal 🎓

A secure, anonymous complaint management system for educational institutions built with MERN stack.

## ✨ Features

- 🔒 **Anonymous Complaints** - Student identity protected from teachers
- 👥 **Role-Based Access** - Student, Teacher, and Admin dashboards
- 🔐 **Admin Approval** - Secure teacher/admin registration
- 📊 **Real-Time Tracking** - Track complaints with unique IDs
- 💬 **Response System** - Teachers respond to assigned complaints
- 📈 **Analytics Dashboard** - Comprehensive statistics and insights

## 🛠️ Tech Stack

**Frontend:**

- React.js 18+
- Tailwind CSS
- React Router DOM
- Axios

**Backend:**

- Node.js
- Express.js
- MongoDB (Mongoose)
- JWT Authentication
- Bcryptjs

## 📋 Prerequisites

- Node.js (v18 or higher)
- MongoDB Atlas account or local MongoDB
- npm or yarn

## 🚀 Quick Start

### 1. Clone the repository

```bash
git clone <your-repo-url>
cd e-grievance-portal
```

### 2. Backend Setup

```bash
cd backend
npm install
```

Create `.env` file in backend folder:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_secret_key_here
```

Start backend server:

```bash
npm run dev
```

### 3. Frontend Setup

```bash
cd frontend
npm install
npm start
```

Frontend runs on: `http://localhost:3000`  
Backend runs on: `http://localhost:5000`

## 👤 User Roles

### Student

- Submit anonymous complaints
- Track complaint status
- View responses

### Teacher

- View assigned complaints (anonymous)
- Respond to complaints
- View analytics

### Admin

- View all complaints with full details
- Assign complaints to teachers
- Approve/reject teacher registrations
- Update complaint status
- View comprehensive analytics

## 🔑 First Admin Setup

**Option 1: Auto-approve first admin (Recommended)**

- First admin registration auto-approves
- Subsequent admins need approval

**Option 2: Manual approval**

```bash
cd backend
node scripts/approveAdmin.js admin@example.com
```

## 📁 Project Structure

```
e-grievance-portal/
├── frontend/               # React frontend
│   ├── src/
│   │   ├── components/    # Reusable components
│   │   ├── pages/         # Page components
│   │   ├── services/      # API services
│   │   ├── context/       # React context
│   │   └── utils/         # Utilities
│   └── package.json
│
├── backend/               # Express backend
│   ├── models/           # Mongoose schemas
│   ├── routes/           # API routes
│   ├── controllers/      # Business logic
│   ├── middleware/       # Auth middleware
│   ├── config/           # Database config
│   ├── scripts/          # Utility scripts
│   └── package.json
│
└── README.md
```

## 🔐 Security Features

- JWT-based authentication
- Password hashing with bcrypt
- Role-based authorization
- Protected API endpoints
- Student anonymity protection
- Admin approval for staff accounts

## 📊 API Endpoints

**Authentication:**

- `POST /api/auth/register` - Register user
- `POST /api/auth/login` - Login user
- `GET /api/auth/me` - Get current user

**Complaints:**

- `POST /api/complaints` - Submit complaint
- `GET /api/complaints` - Get complaints (role-filtered)
- `GET /api/complaints/:id` - Get single complaint
- `PUT /api/complaints/:id/status` - Update status (Admin)
- `PUT /api/complaints/:id/assign` - Assign to teacher (Admin)
- `POST /api/complaints/:id/response` - Add response (Teacher/Admin)
- `GET /api/complaints/track/:trackingId` - Public tracking
- `GET /api/complaints/stats` - Get statistics

**User Management:**

- `GET /api/users/teachers` - Get all teachers (Admin)
- `GET /api/users/pending` - Get pending approvals (Admin)
- `PUT /api/users/:id/approve` - Approve user (Admin)
- `DELETE /api/users/:id/reject` - Reject user (Admin)

## 🧪 Testing

**Test Users:**

```
Student:
- Email: student@test.com
- Password: 123456

Teacher (after approval):
- Email: teacher@test.com
- Password: 123456

Admin:
- Email: admin@test.com
- Password: 123456
```

## 📝 Environment Variables

**Backend (.env):**

```env
PORT=5000
MONGO_URI=mongodb+srv://username:password@cluster.mongodb.net/dbname
JWT_SECRET=your_secret_key_min_32_characters
```

## 🐛 Troubleshooting

**Can't login as teacher/admin:**

- Check if account is approved by admin
- Visit admin dashboard → User Approval page

**MongoDB connection error:**

- Check MONGO_URI in .env
- Verify network access in MongoDB Atlas
- Check IP whitelist

**Port already in use:**

- Change PORT in backend .env
- Update API_URL in frontend src/services/api.js

## 📄 License

This project is for educational purposes.

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit changes (`git commit -m 'Add AmazingFeature'`)
4. Push to branch (`git push origin feature/AmazingFeature`)
5. Open Pull Request

## 📧 Contact

For issues or questions, please open an issue on GitHub.

---

**Built with ❤️ for making campus life better**

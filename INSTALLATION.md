# Installation Guide

## Prerequisites

Before you begin, ensure you have the following installed:

- Node.js (v18 or higher) - [Download](https://nodejs.org/)
- npm (comes with Node.js)
- Git - [Download](https://git-scm.com/)
- MongoDB Atlas account - [Sign up](https://www.mongodb.com/cloud/atlas)

## Step-by-Step Installation

### 1. Clone Repository

```bash
git clone <repository-url>
cd e-grievance-portal
```

### 2. Backend Setup

```bash
# Navigate to backend
cd backend

# Install dependencies
npm install

# Create .env file
touch .env
```

Add the following to `.env`:

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string_here
JWT_SECRET=your_secret_key_at_least_32_characters_long
```

**Getting MongoDB URI:**

1. Login to MongoDB Atlas
2. Click "Connect" on your cluster
3. Choose "Connect your application"
4. Copy the connection string
5. Replace `<password>` with your database password
6. Replace `<dbname>` with your database name (e.g., `egrievance`)

**Start Backend:**

```bash
npm run dev
```

Backend should be running on `http://localhost:5000`

### 3. Frontend Setup

Open a new terminal:

```bash
# Navigate to frontend
cd frontend

# Install dependencies
npm install

# Start frontend
npm start
```

Frontend should open automatically at `http://localhost:3000`

### 4. Create First Admin

**Option 1: Register through UI**

- Go to `http://localhost:3000/register`
- Register as Admin
- First admin will be auto-approved
- Login with your credentials

**Option 2: Use seed script**

```bash
cd backend
npm run seed:admin
```

Default credentials:

- Email: `superadmin@egrievance.com`
- Password: `Admin@123`

## Verification

1. **Backend Health Check**

   - Visit: `http://localhost:5000`
   - Should see: "E-Grievance API is running..."

2. **Frontend Check**

   - Visit: `http://localhost:3000`
   - Should see homepage with login/register buttons

3. **Database Check**
   - Login to MongoDB Atlas
   - Check if database and collections are created

## Common Issues

**Issue: Port already in use**

- Change PORT in backend `.env`
- Or kill process using the port

**Issue: MongoDB connection failed**

- Check MONGO_URI format
- Verify network access in MongoDB Atlas
- Check if IP is whitelisted (0.0.0.0/0 for testing)

**Issue: Can't login as teacher**

- Teachers need admin approval
- Login as admin and approve the teacher

## Next Steps

1. Register test users (student, teacher, admin)
2. Admin approves teacher
3. Student submits complaint
4. Admin assigns to teacher
5. Teacher responds to complaint

## Support

For issues, check:

1. Console logs (browser & terminal)
2. Network tab in browser DevTools
3. MongoDB Atlas logs

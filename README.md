# User Management System with Authentication and Role-Based Access Control

A **User Management System** that provides secure authentication and role-based authorization for **Users** and **Admins**. This project ensures data protection, controlled access, and efficient workflows for different roles.


https://github.com/user-attachments/assets/8b5811c5-2966-4fa6-a6b3-97a7440aac0a


---

## Project Assignment Details

This project implements robust **Authentication** and **Authorization** mechanisms, providing a streamlined user experience while ensuring security. Key features include:

### Authentication

1. **JWT Authentication**:

   - **Sign-Up Flow**:
     - User registers an account.
     - Verification email with OTP is sent.
     - Once the email is verified, a welcome email is sent.
   - **Login Flow**:
     - User logs in with credentials and receives a JWT token.
   - **Forgot Password Flow**:
     - User requests a password reset.
     - A reset password email with a link is sent.
     - User updates the password via the link.
     - A confirmation email is sent after a successful password update.

2. **Google OAuth 2.0 with Passport.js**:
   - Users can sign up and log in using their Google accounts.

---

### Authorization Flow

- **Middleware Setup**:
  - Authorization middleware checks user roles (`User` or `Admin`) to restrict or grant access.
  - Ensures route-specific access control for sensitive data or operations.

---

### Role-Based Access Control

- **Roles**:
  - **User**:
    - Access their personal dashboard and view only their own details.
    - Update the assigned task status.
  - **Admin**:
    - Manage all users.
    - View a list of all usernames and email addresses in the system.
    - Edit the User role (User or Admin).
    - Delete the user.
    - Assign tasks to users.
    - View tasks of any user.

---

## Tech Stack

- **Backend**: Node.js, Express.js
- **Authentication**: JSON Web Tokens (JWT), Passport.js (Google OAuth 2.0)
- **Database**: MongoDB
- **Email Service**: Nodemailer
- **Frontend**: React.js, Zustand

---

## Installation Guide

### Prerequisites

- [Node.js](https://nodejs.org/) (v16 or higher recommended)
- [MongoDB](https://www.mongodb.com/) (installed locally or access to a MongoDB cloud instance)
- [Git](https://git-scm.com/)
- A valid Google OAuth Client ID and Secret
- An email account for sending notifications (e.g., Gmail)

---

### Steps

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/ShreyamKundu/RBAC_ASG.git
   cd RBAC_ASG
   ```

2. **Install Backend Dependencies**:

   ```bash
   cd backend
   npm install
   ```

3. **Configure Backend Environment Variables**:
   Create a `.env` file in the `backend` directory and add the following:

   ```plaintext
   MONGO_URI = your mongo url
   JWT_SECRET= your jwt secret
   NODE_ENV= 'development'
   CLIENT_URL= http://localhost:5173/
   EMAIL_USER= 'your email address'
   EMAIL_PASSWORD= 'your email password'
   GOOGLE_CLIENT_ID=
   GOOGLE_CLIENT_SECRET=
   GOOGLE_REDIRECT_URI=http://localhost:5000/auth/google/callback
   SESSION_SECRET= 'your session secret'
   ```

4. **Install Frontend Dependencies**:

   ```bash
   cd ../frontend
   npm install
   ```

5. **Start the Backend Server**:
   In the `backend` directory:

   ```bash
   npm start
   ```

7. **Start the Frontend Development Server**:
   In the `frontend` directory:

   ```bash
   npm run dev
   ```

8. **Open in Browser**:
   Navigate to [http://localhost:5173](http://localhost:5173) to access the application.

---

### Additional Notes

1. **Database Setup**:

   - Ensure MongoDB is running locally or provide the URI to your MongoDB cloud instance in the `.env` file.

2. **Google OAuth**:

   - Create a project in the [Google Developer Console](https://console.developers.google.com/).
   - Configure the OAuth consent screen and generate client credentials.
   - Set the redirect URI to `http://localhost:5000/api/auth/google/callback`.

3. **Email Service**:

   - Use a service like Gmail for testing email functionality.
   - Enable "Allow less secure apps" or generate an App Password for better security.

4. **Testing**:
   - Test all authentication and authorization flows to ensure proper setup.
   - Verify email notifications, JWT issuance, and RBAC functionality.

---

Your local setup is now complete! 🎉


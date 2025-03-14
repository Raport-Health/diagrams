# DOS

## Features
- **Authentication**: Supports JWT, and Google OAuth.
- **Database**: Uses MongoDB with Mongoose ORM.
- **File Uploads**: Handles file uploads with Multer and AWS S3.
- **Security**: Implements bcrypt for password hashing and validation.
- **Email Support**: Sends emails using Nodemailer.
- **Session Management**: Uses Express-session and cookie-parser.
- **Validation**: Ensures data integrity with Validator.

## Tech Stack
- **Backend**: Node.js, Express.js
- **Database**: MongoDB, Mongoose
- **Authentication**: JWT, Passport.js (Google & Facebook OAuth)
- **Storage**: AWS S3
- **Email Service**: Nodemailer
- **Validation**: Validator

## Installation
### Prerequisites
- Node.js (>= 16.x)
- MongoDB instance
- AWS S3 credentials (if using file uploads)

### Steps
1. Clone the repository:
   ```sh
   git clone
   cd project
   ```
2. Install dependencies:
   ```sh
   npm install
   ```
3. Set up environment variables:
   Create a `.env` file in the root directory and add the following:
   ```env
   PORT=5000
   MONGO_URI=your_mongodb_uri
   JWT_SECRET=your_jwt_secret
   AWS_ACCESS_KEY=your_aws_access_key
   AWS_SECRET_KEY=your_aws_secret_key
   AWS_BUCKET_NAME=your_s3_bucket
   GOOGLE_CLIENT_ID=your_google_client_id
   GOOGLE_CLIENT_SECRET=your_google_client_secret
   FACEBOOK_APP_ID=your_facebook_app_id
   FACEBOOK_APP_SECRET=your_facebook_app_secret
   ```

## Running the Application
### Development
```sh
npm run dev
```
### Production
```sh
npm start
```

## API Endpoints
| Method | Endpoint          | Description                 |
|--------|------------------|-----------------------------|
| POST   | /api/auth/login  | User login                  |
| POST   | /api/auth/signup | User registration           |
| GET    | /api/user/profile | Get user profile data       |
| POST   | /api/upload      | Upload file to AWS S3       |

## Deployment
This app can be deployed on:
- **AWS EC2**
- **Heroku**
- **DigitalOcean**
- **VPS Servers**

## Contribution
Feel free to fork the repository and submit a pull request for improvements.

## License
MIT License © 2025 Your Name


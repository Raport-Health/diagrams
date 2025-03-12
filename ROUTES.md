# API Routes Documentation

## Table of Contents
- [Authentication Routes](#authentication-routes)
- [Document Routes](#document-routes)
- [Folder Routes](#folder-routes)
- [Summaries Routes](#summaries-routes)
- [Chat Routes](#chat-routes)
- [Admin Document Management](#admin-document-management)

## Authentication Routes
Base Path: `/api`

### Authentication & Registration
1. `POST /auth/register-user-api`
   - Purpose: Register a new user
   - Controller: `registerApi`
   - Backend Definition: 
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage: 
     - Service defined in: `src/store/auth/services.js:registerFunApi`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in registration components

2. `POST /auth/login`
   - Purpose: User login
   - Controller: `loginApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js:loginFunApi`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in: `src/pages/LoginPage.jsx`

3. `POST /auth/verifyOtp`
   - Purpose: Verify OTP for authentication
   - Controller: `verifyOtpApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in OTP verification components

4. `GET /auth/logout`
   - Purpose: User logout
   - Requires: Authentication
   - Controller: `logoutApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in header/navbar components for logout functionality

5. `GET /auth/token-is-valid`
   - Purpose: Validate authentication token
   - Requires: Authentication
   - Controller: `checkTokenIsValidApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in authentication middleware and session validation

6. `POST /auth/health-provider-detail`
   - Purpose: Register health provider information
   - Controller: `healthProviderApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js:healthProviderDetailFunApi`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in provider registration flows

### Password Management
1. `POST /auth/forget-password`
   - Purpose: Initiate forgot password process
   - Controller: `forgetPasswordApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in password recovery flows

2. `POST /auth/reset-password`
   - Purpose: Reset password
   - Controller: `resetPasswordApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in password reset components

3. `POST /change-password`
   - Purpose: Change user password
   - Requires: Authentication
   - Controller: `changePasswordApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in profile management components

4. `POST /admin/reset-password`
   - Purpose: Change admin password
   - Controller: `changeAdminPasswordApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Used in admin dashboard components

### User Management
1. `GET /auth/get-all-users`
   - Purpose: Retrieve all users with pagination
   - Requires: Authentication
   - Controller: `getAllUsersApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in: `src/pages/AdminDashboard/AdminUserManagement.jsx`

2. `POST /auth/get-user-details`
   - Purpose: Get specific user details
   - Controller: `getUserbyId`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in profile components and user detail views

3. `POST /auth/update-user-details`
   - Purpose: Update user profile
   - Controller: `UpdateUserApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js:updateUserDetailsFunApi`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in: `src/pages/Dashboard/ProfileUpdate.jsx`

4. `POST /user-auto-login-api`
   - Purpose: Automatic login with token
   - Requires: Authentication
   - Controller: `UserAutoLoginApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in app initialization and session restoration

### Admin Management
1. `POST /auth/send-admin-request-api`
   - Purpose: Send admin invitation
   - Controller: `SentInvitationAdminApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in: `src/pages/AdminDashboard/AdminInvitation.jsx`

2. `POST /auth/create-new-admin-api`
   - Purpose: Create new admin account
   - Controller: `createNewAdminApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in admin creation flows

3. `GET /auth/get-all-admins-api`
   - Purpose: List all admins
   - Controller: `GetAllAdminsApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Constants defined in: `src/store/auth/constrants.js`
     - Used in admin management components

4. `PUT /auth/update-admin-api/:id`
   - Purpose: Update admin details
   - Requires: Authentication
   - Controller: `updateAdmin`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in admin profile management

### Account Management
1. `POST /auth/account-status-change`
   - Purpose: Change account activation status
   - Controller: `ActivateUserAccount`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in user management components

2. `GET /admin/delete/:adminId`
   - Purpose: Delete admin account
   - Controller: `deleteAdminApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in admin management components

3. `GET /user/delete/:id`
   - Purpose: Delete user account
   - Controller: `deleteUserApi`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in user management components

### KYC Management
1. `PATCH /admin/kyc/update`
   - Purpose: Update KYC status
   - Controller: `UpdateKycStatus`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in: `src/pages/AdminDashboard/KycManagement.jsx`

2. `GET /admin/kyc`
   - Purpose: Get all KYC data
   - Controller: `GetAllKycData`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in: `src/pages/AdminDashboard/KycManagement.jsx`

3. `GET /kyc/status`
   - Purpose: Get user's KYC status
   - Requires: Authentication
   - Controller: `GetMyKycStatus`
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Controller implemented in: `controllers/AuthController.js`
   - Frontend Usage:
     - Service defined in: `src/store/auth/services.js`
     - Used in: `src/pages/Dashboard/ProfileUpdate.jsx`

### OAuth Routes
1. `GET /auth/google`
   - Purpose: Google OAuth login
   - Scope: profile, email
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Uses Passport.js for authentication
   - Frontend Usage:
     - Used in login components with OAuth options

2. `GET /auth/google/callback`
   - Purpose: Google OAuth callback
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Handles OAuth response processing
   - Frontend Usage:
     - Not directly called from frontend (server-side redirect)

3. `GET /auth/facebook`
   - Purpose: Facebook OAuth login
   - Scope: email
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Uses Passport.js for authentication
   - Frontend Usage:
     - Used in login components with OAuth options

4. `GET /auth/facebook/callback`
   - Purpose: Facebook OAuth callback
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Handles OAuth response processing
   - Frontend Usage:
     - Not directly called from frontend (server-side redirect)

5. `GET /login/success`
   - Purpose: Handle successful OAuth login
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Returns user data after authentication
   - Frontend Usage:
     - Used in OAuth flow completion

6. `GET /login/failed`
   - Purpose: Handle failed OAuth login
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Returns error for failed authentication
   - Frontend Usage:
     - Used in OAuth error handling

7. `GET /logout`
   - Purpose: Alternative logout endpoint
   - Backend Definition:
     - Route defined in: `routes/authRoutes.js`
     - Ends Passport.js session
   - Frontend Usage:
     - Used in OAuth logout flows

## Document Routes
Base Path: `/api/doc`

### Document Management
1. `POST /uploadDocsApi`
   - Purpose: Upload multiple documents
   - Accepts: Multiple files
   - Controller: `uploadDocsApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js:UploadDocumentApi`
     - Constants defined in: `src/store/document/contraints.js`
     - Used in: `src/pages/Dashboard/DocUpload.jsx`

2. `GET /getAllDocsApi`
   - Purpose: Retrieve all documents
   - Requires: Authentication
   - Controller: `getAllDocsApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js:getallDocsFunApi`
     - Constants defined in: `src/store/document/contraints.js`
     - Used in: `src/pages/Dashboard/DocumentManagment.jsx`

3. `GET /getAllDocsForSummary`
   - Purpose: Get documents for summary generation
   - Requires: Authentication
   - Controller: `getAllDocsForSummary`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js:getallDocsFunApi`
     - Constants defined in: `src/store/document/contraints.js`
     - Used in: `src/pages/Dashboard/Summeries.jsx`

### Document Labels and Categories
1. `POST /addDocsLabelApi`
   - Purpose: Add labels to documents
   - Controller: `addDocsLabelApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in document labeling components

2. `POST /editDocsLabelApi`
   - Purpose: Edit document labels
   - Controller: `EditDocsLabelApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in document editing components

3. `POST /update-docs-category`
   - Purpose: Update document category
   - Controller: `updateDocsCategoryApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js:updateDocsCategoryApi`
     - Constants defined in: `src/store/document/contraints.js`
     - Used in document organization components

4. `POST /categorize-docs-api`
   - Purpose: Categorize documents
   - Controller: `CategorizeDocsApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in document categorization flows

### Document Deletion
1. `POST /deleteDocsApi`
   - Purpose: Delete documents (user level)
   - Controller: `DeleteDocsApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js:deleteDocsFunApi`
     - Constants defined in: `src/store/document/contraints.js`
     - Used in: `src/pages/Dashboard/DocumentManagment.jsx`

2. `GET /deleteDocsApi/:docsId`
   - Purpose: Delete documents (admin level)
   - Controller: `DeleteDocsApiAdmin`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in: `src/pages/AdminDashboard/AdminDocumentManagment.jsx`

### Patient Management
1. `GET /get-all-patient-api`
   - Purpose: Get list of all patients
   - Controller: `getallPatient`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in patient selection components and document assignment flows

2. `POST /assignDocstoPatientApi`
   - Purpose: Assign documents to patient
   - Accepts: Single file
   - Controller: `AssignDocstoPatientApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in: `src/component/Layout/Dashboard/DocumentAssignModel.jsx`

### Category Management
1. `POST /add-category-api`
   - Purpose: Add new categories
   - Controller: `AddCategoriesApi`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in category management components

2. `GET /get-all-categories`
   - Purpose: Get list of all categories
   - Controller: `getallCategories`
   - Backend Definition:
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in: `src/component/Layout/Dashboard/DocumentAssignModel.jsx`
     - Used in document organization components

## Folder Routes
Base Path: `/api/folder`

1. `POST /add-folder-Api`
   - Purpose: Create a new folder
   - Controller: `createFolderApi`
   - Backend Definition:
     - Route defined in: `routes/folderRoutes.js`
     - Controller implemented in: `controllers/FolderController.js`
   - Frontend Usage:
     - Service defined in: `src/store/folder/services.js`
     - Used in folder creation components and document organization flows

2. `POST /add-docs-to-folder-Api`
   - Purpose: Add documents to an existing folder
   - Controller: `addDocumentToFolderApi`
   - Backend Definition:
     - Route defined in: `routes/folderRoutes.js`
     - Controller implemented in: `controllers/FolderController.js`
   - Frontend Usage:
     - Service defined in: `src/store/folder/services.js`
     - Used in document organization components and folder management

## Summaries Routes
Base Path: `/api/summeries`

1. `POST /document-Summeries`
   - Purpose: Save document summaries
   - Accepts: Single file
   - Controller: `saveDocumentSummeriesApi`
   - Backend Definition:
     - Route defined in: `routes/summeriesRoutes.js`
     - Controller implemented in: `controllers/SummeriesController.js`
   - Frontend Usage:
     - Service defined in: `src/store/summary/services.js:AlDocsSummaryApi`
     - Constants defined in: `src/store/summary/contraints.js`
     - Used in: `src/pages/Dashboard/Summeries.jsx`

2. `POST /file-summeries`
   - Purpose: Process and summarize files (audio/video)
   - Accepts: Single file
   - Controller: `saveFileSummeriesApi`
   - Backend Definition:
     - Route defined in: `routes/fileSummeriesRoutes.js`
     - Controller implemented in: `controllers/SummeriesController.js`
   - Frontend Usage:
     - Service defined in: `src/store/summary/services.js:AlDocsSummaryApi`
     - Constants defined in: `src/store/summary/contraints.js`
     - Used in audio/video processing components and summary generation

## Chat Routes
Base Path: `/api/chat`

1. `POST /`
   - Purpose: Send a regular chat message
   - Controller: `chatController.sendMessage`
   - Backend Definition:
     - Route defined in: `routes/chatRoutes.js`
     - Controller implemented in: `controllers/chatController.js`
   - Frontend Usage:
     - Service defined in: `src/store/chat/services.js:sendMessage`
     - Used in: `src/pages/Dashboard/ChatWithAi.jsx`
     - Handles general AI chat functionality

2. `POST /context`
   - Purpose: Send a context-aware chat message
   - Requires: Authentication
   - Controller: `contextchatController.sendMessage`
   - Backend Definition:
     - Route defined in: `routes/chatRoutes.js`
     - Controller implemented in: `controllers/chatController.js`
   - Frontend Usage:
     - Service defined in: `src/store/chat/services.js:sendContextMessage`
     - Used in: `src/pages/Dashboard/ContextChat.jsx`
     - Provides document-aware chat functionality with context from user documents

## Admin Document Management
1. `POST /doc/uploadDocsApi` (Admin Context)
   - Purpose: Admin document upload
   - Accepts: Multiple files
   - Backend Definition:
     - Uses same route as regular upload but with admin privileges
     - Route defined in: `routes/documentRoutes.js`
     - Controller implemented in: `controllers/DocumentController.js`
   - Frontend Usage:
     - Service defined in: `src/store/document/services.js`
     - Used in: `src/pages/AdminDashboard/DocumentUploadSection.jsx`
     - Uses same service as regular upload but with admin context
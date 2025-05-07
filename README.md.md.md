

# Blog App Deployment (MERN Stack on AWS Free Tier)

This project demonstrates deploying a Blog app using the MERN stack with AWS free-tier eligible services:

- **Backend**: Express.js on EC2
- **Frontend**: React on S3 (Static Website Hosting)
- **Media Uploads**: S3 bucket for images and files

---

## Steps I Followed 

### 1. Frontend S3 Setup

- Created bucket: `soso-blogapp-frontend`
- Enabled public access
- Activated Static Website Hosting
- Deployed the frontend build to the S3 bucket
- Access the app via the link:  
  `http://maha-blogapp-frontend.s3-website.eu-north-1.amazonaws.com`

### 2. Media Uploads S3 Bucket

- Created bucket: `soso-blogapp-media`
- Enabled CORS for browser uploads
- Tested uploading an image to the bucket

### 3. IAM User and Permissions for Media Access

- Created IAM user: `blog-app-user`
- Granted the user permissions to access only the media bucket
- Saved Access Key and Secret Key (not shared here)

### 4. EC2 Backend Setup

- Launched EC2 instance (Ubuntu) in `eu-north-1`
- Opened the necessary ports (22, 80, 443, 5000)
- SSH into the instance, installed Node.js, PM2, and AWS CLI
- Cloned the project repository, configured `.env` file
- Started the server with PM2

### 5. Frontend Deployment

- Set the backend API and media bucket URL in the frontend `.env`
- Built the frontend using `pnpm run build`
- Deployed the build to the S3 bucket via AWS CLI

---

## Screenshots 

- S3 frontend site up and running
- `curl -I` command output showing 200 OK
- Image upload to the media S3 bucket
- Backend running via PM2 on EC2


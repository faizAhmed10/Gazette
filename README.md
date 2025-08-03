# Gazette - Modern Content Publishing Platform

## Project Overview

Gazette is a comprehensive content publishing platform that connects authors and readers through a modern, responsive web interface. The platform consists of three main components:

1. **Author Portal** - A dedicated interface for content creators to write, edit, and manage their articles
2. **Reader Portal** - An engaging platform for users to discover, read, and interact with published content
3. **Backend API** - A robust Django REST API that powers both portals with secure authentication and data management

## Key Features

### Author Portal
- Secure authentication system with JWT tokens
- Rich text editor with ReactQuill for creating and editing articles
- Article management dashboard with status tracking (draft/published)
- Image upload capability with Cloudinary integration
- Category management for content organization
- Article preview functionality before publishing

### Reader Portal
- User registration and authentication
- Personalized content feed
- Advanced filtering by author, category, and date
- Nested comment system for article discussions
- Responsive design for optimal viewing on all devices

### Backend API
- RESTful architecture using Django REST Framework
- JWT-based authentication with token refresh
- Hierarchical comment system using django-mptt
- Cloud-based image storage with Cloudinary
- Comprehensive API endpoints for both author and reader operations

## Technical Stack

### Frontend (Author & Reader Portals)
- **React** - Component-based UI library
- **Vite** - Next-generation frontend tooling
- **TailwindCSS** - Utility-first CSS framework for responsive design
- **React Router** - Client-side routing
- **JWT Decode** - Token handling for authentication
- **React Toastify** - Toast notifications
- **React Icons** - Icon library
- **ReactQuill** - Rich text editor (Author Portal)

### Backend
- **Django** - High-level Python web framework
- **Django REST Framework** - Toolkit for building Web APIs
- **Simple JWT** - JWT authentication for Django REST Framework
- **django-mptt** - Modified Preorder Tree Traversal for hierarchical data
- **Cloudinary** - Cloud-based image management
- **SQLite** - Database (development)

## Architecture

The application follows a modern client-server architecture:

1. **Frontend**: Two separate React applications (Author and Reader portals) that communicate with the backend API
2. **Backend**: Django REST API that handles data processing, authentication, and business logic
3. **Database**: Stores user data, articles, comments, and relationships
4. **Cloud Storage**: Manages media files (images) through Cloudinary

## Security Features

- JWT-based authentication with token refresh mechanism
- Role-based access control (author vs. reader)
- Password validation and secure storage
- Protected API endpoints with proper authorization checks
- Environment variable management for sensitive information

## Installation and Setup

### Prerequisites
- Node.js (v14+)
- Python (v3.8+)
- Git

### Backend Setup

```bash
# Clone the repository
git clone <repository-url>
cd gazette-backend-main/backend

# Create a virtual environment
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt

# Apply migrations
python manage.py migrate

# Create a superuser (optional)
python manage.py createsuperuser

# Run the development server
python manage.py runserver
```

### Author Portal Setup

```bash
# Navigate to the author portal directory
cd ../../gazette-author-portal-main

# Install dependencies
npm install

# Create .env file with the following content
VITE_BACKEND_URL=http://localhost:8000/
VITE_IMAGE_URL=https://res.cloudinary.com/your-cloudinary-name/

# Start the development server
npm start
```

### Reader Portal Setup

```bash
# Navigate to the reader portal directory
cd ../gazette-reader-portal-main

# Install dependencies
npm install

# Create .env file with the following content
VITE_BACKEND_URL=http://localhost:8000/
VITE_IMAGE_URL=https://res.cloudinary.com/your-cloudinary-name/

# Start the development server
npm run dev
```

## Project Structure

```
gazette/
├── gazette-author-portal-main/   # Author interface
│   ├── public/                   # Static assets
│   └── src/                      # React source code
│       ├── components/           # Reusable UI components
│       ├── pages/                # Page components
│       └── utils/                # Utility functions and context
│
├── gazette-reader-portal-main/   # Reader interface
│   ├── public/                   # Static assets
│   └── src/                      # React source code
│       ├── components/           # Reusable UI components
│       ├── pages/                # Page components
│       └── utils/                # Utility functions and context
│
└── gazette-backend-main/         # Backend API
    └── backend/                  # Django project
        ├── api/                  # API app
        │   ├── migrations/       # Database migrations
        │   ├── models.py         # Data models
        │   ├── serializers/      # DRF serializers
        │   ├── urls_dir/         # URL routing
        │   └── views/            # API endpoints
        └── backend/              # Project settings
```

## Development Approach

This project demonstrates a comprehensive understanding of full-stack web development with a focus on:

1. **Separation of Concerns** - Clear distinction between frontend and backend responsibilities
2. **Component-Based Architecture** - Reusable UI components for maintainable code
3. **RESTful API Design** - Well-structured endpoints following REST principles
4. **Authentication & Authorization** - Secure user management and access control
5. **Responsive Design** - Mobile-first approach for optimal user experience across devices
6. **State Management** - Context API for efficient state handling
7. **Error Handling** - Comprehensive error management with user feedback

## Future Enhancements

- Implement search functionality with advanced filtering
- Add social sharing capabilities for articles
- Integrate analytics for author insights
- Implement bookmarking and favorites for readers
- Add support for multimedia content (videos, podcasts)
- Implement a notification system

## Conclusion

Gazette demonstrates a modern approach to content publishing platforms with a focus on user experience, performance, and maintainability. The separation into distinct portals for authors and readers allows for tailored experiences while maintaining a consistent design language and technical foundation.

---

© 2024 Gazette. All rights reserved.
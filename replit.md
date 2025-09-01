# HarrshRealityy - Anonymous Imageboard Application

## Overview

HarrshRealityy is a full-stack anonymous imageboard application built with React and Express, styled after traditional imageboard platforms like 4chan. The application allows users to create boards, post threads with optional images, and reply to existing threads. It features a classic imageboard interface with board navigation, thread management, and file upload capabilities for images, designed to be as uncensored as possible within legal boundaries.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **Routing**: Wouter for client-side routing with pages for home, board view, thread view, and admin
- **State Management**: TanStack Query (React Query) for server state management and caching
- **UI Framework**: Radix UI components with shadcn/ui design system
- **Styling**: Tailwind CSS with CSS variables for theming, dark mode support with orange accent colors
- **Form Handling**: React Hook Form with Zod validation schemas

### Backend Architecture
- **Runtime**: Node.js with Express.js REST API
- **Language**: TypeScript with ES modules
- **Development**: TSX for development server with hot reloading
- **File Uploads**: Multer middleware for handling image uploads with file type validation
- **Static Files**: Express static middleware for serving uploaded images
- **API Design**: RESTful endpoints for boards, threads, and posts with proper HTTP status codes

### Data Storage Solutions
- **Database**: PostgreSQL with Drizzle ORM for type-safe database operations
- **Connection**: Neon Database serverless PostgreSQL connection
- **Schema**: Relational design with boards, threads, and posts tables
- **Migrations**: Drizzle Kit for database schema migrations
- **Development Storage**: In-memory storage implementation for development/testing

### Database Schema Design
- **Boards**: Store board metadata (code, name, description, active status)
- **Threads**: Original posts with subject, content, author, images, and metadata
- **Posts**: Replies to threads with content, author, optional images, and reply references
- **Relationships**: Proper foreign key relationships between boards → threads → posts
- **Post Numbering**: Sequential post numbers per board for traditional imageboard feel

### Authentication and Authorization
- **Anonymous Posts**: No user authentication required, traditional imageboard approach
- **Admin Features**: Basic admin panel for board management and content moderation
- **Content Moderation**: Delete functionality for threads and posts through admin interface

### File Upload System
- **Storage**: Local file system storage in uploads directory
- **Validation**: File type restrictions (JPEG, PNG, GIF, WebP) with 10MB size limit
- **Serving**: Static file serving through Express with proper MIME types
- **Security**: File type validation and size limits to prevent abuse

### UI/UX Design Patterns
- **Imageboard Aesthetic**: Traditional imageboard styling with orange accent theme
- **Responsive Design**: Mobile-friendly layout using Tailwind responsive utilities
- **Component Library**: Comprehensive UI components from Radix UI/shadcn
- **Navigation**: Board navigation bar and header with consistent branding
- **Form Design**: Inline forms for creating threads and posts with file upload

### API Structure
- **RESTful Design**: Standard HTTP methods (GET, POST, DELETE) for resource operations
- **Board Management**: CRUD operations for boards with admin capabilities
- **Thread Operations**: Create threads, view thread lists, delete threads
- **Post Management**: Create replies, view posts in threads, delete posts
- **File Handling**: Multipart form data handling for image uploads
- **Error Handling**: Consistent error responses with proper HTTP status codes
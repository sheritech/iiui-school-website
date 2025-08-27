# Overview

This is a comprehensive school management system for IIUI School Mardan built with a full-stack TypeScript architecture. The application provides a multi-portal system serving parents, students, teachers, and administrators with features including admissions management, contact forms, news publishing, and user authentication through Replit Auth.

# User Preferences

Preferred communication style: Simple, everyday language.

# System Architecture

## Frontend Architecture
- **Framework**: React 18 with TypeScript using Vite as the build tool
- **UI Library**: shadcn/ui components built on top of Radix UI primitives
- **Styling**: Tailwind CSS with custom design tokens and CSS variables
- **State Management**: TanStack Query (React Query) for server state management
- **Routing**: Wouter for client-side routing
- **Forms**: React Hook Form with Zod validation and @hookform/resolvers
- **Internationalization**: Custom i18n implementation supporting English and Urdu languages

## Backend Architecture
- **Runtime**: Node.js with Express.js framework
- **Language**: TypeScript with ES modules
- **Database ORM**: Drizzle ORM with PostgreSQL dialect
- **Authentication**: Replit Auth integration with OpenID Connect
- **Session Management**: Express sessions with PostgreSQL store using connect-pg-simple
- **API Design**: RESTful endpoints with centralized error handling

## Database Schema Design
The application uses PostgreSQL with the following core entities:
- **Users**: Central user management with role-based access (parent, student, teacher, admin)
- **Students**: Academic records linked to users and parents
- **Sessions**: Required for Replit Auth session storage
- **News**: Content management for school announcements
- **Contact Submissions**: Form submissions from website visitors
- **Admissions**: Application management system

The schema uses UUID primary keys and maintains referential integrity with foreign key relationships.

## Authentication & Authorization
- **Provider**: Replit Auth with OpenID Connect discovery
- **Session Storage**: PostgreSQL-backed sessions with 1-week TTL
- **User Management**: Automatic user creation/updates via upsert operations
- **Role-Based Access**: Four distinct user roles with different portal access levels

## Development & Deployment
- **Build System**: Vite for frontend, esbuild for backend bundling
- **Development**: Hot module replacement with Vite dev server
- **Production**: Static file serving with Express in production mode
- **Database Migrations**: Drizzle Kit for schema management and migrations

# External Dependencies

## Database & Infrastructure
- **Neon Database**: PostgreSQL hosting via @neondatabase/serverless
- **WebSocket Support**: ws package for Neon serverless connections

## Authentication Services
- **Replit Auth**: OpenID Connect authentication provider
- **Passport.js**: Authentication middleware with openid-client strategy

## UI & Styling Dependencies
- **Radix UI**: Complete set of unstyled, accessible UI primitives
- **Tailwind CSS**: Utility-first CSS framework with custom configuration
- **Lucide React**: Icon library for consistent iconography
- **Class Variance Authority**: Utility for managing component variants

## Form & Validation
- **React Hook Form**: Performance-focused form library
- **Zod**: TypeScript-first schema validation
- **Drizzle Zod**: Integration between Drizzle ORM and Zod schemas

## Development Tools
- **TypeScript**: Static type checking across the full stack
- **Vite Plugins**: Runtime error overlay and Replit-specific tooling
- **PostCSS**: CSS processing with Tailwind and Autoprefixer

## Asset Management
- **Static Assets**: Images stored in attached_assets directory
- **Font Loading**: Google Fonts integration (Inter, Open Sans, DM Sans, etc.)
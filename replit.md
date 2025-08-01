# replit.md

## Overview

Fluenti is a comprehensive speech therapy and emotional support platform designed to help individuals, particularly children, improve their communication skills and receive emotional assistance. The application combines speech recognition technology, AI-powered emotional analysis, and interactive therapy exercises to provide personalized learning experiences.

## User Preferences

Preferred communication style: Simple, everyday language.

## System Architecture

### Frontend Architecture

- **Framework**: React 18 with TypeScript
- **Routing**: Wouter for lightweight client-side routing with role-based route protection
- **UI Framework**: Shadcn/ui components with Radix UI primitives
- **Styling**: Tailwind CSS with custom design tokens and role-specific theming
- **State Management**: TanStack Query for server state management
- **Authentication**: Role-based access control with user type-specific interfaces
- **Component Architecture**: Role-based component rendering and route protection
- **Build Tool**: Vite for fast development and optimized builds

### Backend Architecture

- **Runtime**: Node.js with Express.js server
- **Language**: TypeScript with ES modules
- **Database**: MongoDB with Mongoose ODM for flexible document storage
- **Authentication**: Local development auth with session-based user management
- **Session Management**: Express sessions with memory store for development
- **WebSocket**: Real-time communication for chat features
- **Role-Based Access**: User type-specific API endpoints and data filtering

### API Design

- RESTful API endpoints under `/api` prefix
- Authentication middleware protecting sensitive routes
- Speech therapy endpoints for sessions and recordings
- Chat endpoints for emotional support
- WebSocket integration for real-time messaging

## Key Components

### Authentication System

- **Local Development Auth**: Simplified authentication for local development
- **Role-Based Access Control**: Multi-user type system (child/adult/guardian)
- **Session Storage**: MongoDB-backed user sessions with role persistence
- **User Management**: Complete user lifecycle with profile and role management
- **Dashboard Routing**: Automatic redirect to role-appropriate interfaces

### Speech Therapy Module

- **Speech Recognition**: Browser-based Web Speech API integration
- **AI Feedback**: OpenAI GPT-4o powered pronunciation analysis
- **Exercise System**: Structured therapy sessions with progress tracking
- **Assessment Tools**: Comprehensive speech evaluation capabilities
- **Multi-language Support**: English and Urdu language exercises

### Emotional Support System

- **AI Chat Interface**: Conversational emotional support using OpenAI
- **Emotion Detection**: Real-time emotion analysis from text and voice
- **CBT Techniques**: Evidence-based therapeutic responses
- **Crisis Support**: Appropriate escalation for serious concerns

### Progress Tracking

- **Analytics Dashboard**: Visual progress charts and statistics
- **Achievement System**: Gamified learning with streaks and badges
- **Session History**: Detailed record of all therapy sessions
- **Performance Metrics**: Accuracy scores and improvement tracking

## Data Flow

### User Authentication Flow

1. User accesses protected route
2. Replit Auth middleware validates session
3. User profile retrieved from PostgreSQL
4. Session state maintained across requests

### Speech Therapy Flow

1. User initiates therapy session
2. Exercise data loaded from database
3. Speech recognition captures user input
4. AI analysis provides immediate feedback
5. Progress updated in real-time
6. Session results stored for tracking

### Emotional Support Flow

1. User sends message through chat interface
2. Message analyzed for emotional content
3. AI generates appropriate therapeutic response
4. Conversation history maintained
5. Session data stored for continuity

## External Dependencies

### Database Services

- **MongoDB**: Document-based NoSQL database for flexible data storage
- **Mongoose ODM**: Object document mapping with schema validation
- **Local Development**: MongoDB running locally with data persistence

### AI Services

- **OpenAI GPT-4o**: Speech feedback and emotional support
- **Speech Recognition**: Browser Web Speech API
- **Text-to-Speech**: Browser Speech Synthesis API

### UI Libraries

- **Shadcn/ui**: Complete component library
- **Radix UI**: Accessible primitive components
- **Lucide React**: Icon library
- **TanStack Query**: Server state management
- **React Hook Form**: Form validation and management

### Development Tools

- **Vite**: Build tool and development server
- **TypeScript**: Type safety across the stack
- **Tailwind CSS**: Utility-first styling
- **ESLint/Prettier**: Code quality and formatting

## Deployment Strategy

### Production Build

- Frontend built with Vite to `dist/public`
- Backend compiled with esbuild to `dist/index.js`
- Static assets served by Express in production
- Environment variables for database and API keys

### Development Environment

- Vite dev server with HMR for frontend
- tsx for TypeScript execution in development
- Automatic database migrations with Drizzle
- WebSocket support for real-time features

### Database Management

- Drizzle migrations in `migrations/` directory
- Schema definitions in `shared/schema.ts`
- Automatic migration execution on deployment
- Connection pooling for performance optimization

### Security Considerations

- Replit Auth for secure authentication
- Environment variables for sensitive data
- CORS and security headers configured
- Session-based authentication with secure cookies
- Input validation and sanitization

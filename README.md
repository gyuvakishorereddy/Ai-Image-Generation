# 100xPhoto - AI Image Generation Platform

100xPhoto is a powerful AI image platform that lets you generate stunning images and train custom AI models. Built with cutting-edge technology, it enables users to create unique AI-generated artwork and train personalized models on their own image datasets. Whether you're an artist looking to expand your creative possibilities or a developer building AI-powered image applications, 100xPhoto provides an intuitive interface and robust capabilities for AI image generation and model training.

## Table of Contents

- [Tech Stack](#tech-stack)
- [Project Structure](#project-structure)
- [Getting Started](#getting-started)
- [Development Commands](#development-commands)
- [Docker Setup](#docker-setup)
- [Contributing](#contributing)
- [License](#license)

## Tech Stack

- **Frontend**: Next.js 14 (App Router), TypeScript, Tailwind CSS, Shadcn/UI
- **Backend**: Node.js with TypeScript
- **Authentication**: Clerk
- **Payments**: Stripe
- **Database**: Prisma ORM
- **Containerization**: Docker
- **Package Management**: Bun
- **Monorepo Management**: Turborepo

## Project Structure

### Apps and Packages

- `apps/web`: Next.js frontend application with dashboard, image generation, and payment pages
- `apps/backend`: Node.js backend service with payment and webhook routes
- `packages/ui`: Shared React component library
- `packages/db`: Prisma database schema and migrations
- `packages/common`: Shared types and utilities
- `packages/typescript-config`: Shared TypeScript configurations
- `packages/eslint-config`: Shared ESLint configurations

## Getting Started

### Prerequisites

- [Bun](https://bun.sh/) (package manager and runtime)
- [Docker](https://www.docker.com/) (for containerization)
- Clerk Account (for authentication)
- Stripe Account (for payments)

### Environment Setup

Create the following environment files in your workspace:

**apps/web/.env.local**

```bash
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=your_publishable_key
CLERK_SECRET_KEY=your_secret_key
NEXT_PUBLIC_BACKEND_URL=http://localhost:8080
NEXT_PUBLIC_STRIPE_KEY=your_stripe_publishable_key
```

**apps/backend/.env**

```bash
DATABASE_URL=your_database_url
STRIPE_SECRET_KEY=your_stripe_secret_key
```

### Local Development

```bash
# Install all dependencies
bun install

# Run development servers (frontend + backend)
bun run dev

# Build all packages
bun run build

# Run linting
bun run lint
```

## Features

- AI-powered image generation
- User authentication and authorization with Clerk
- Image gallery with preview
- Download generated images
- Responsive design with dark mode support
- Payment processing with Stripe
- Custom AI model training

## Development Commands

```bash
# Run frontend only
bun run start:web

# Run backend only
bun run start:backend

# Run both frontend and backend
bun run dev
```

## Docker Setup

### Environment Variables Required

```bash
# Frontend Environment Variables
NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_live_Y2xlcmsuMTAweGRldnMuY29tJA
NEXT_PUBLIC_BACKEND_URL=https://api.photoaiv2.100xdevs.com
NEXT_PUBLIC_STRIPE_KEY=pk_test_51QsCmFEI53oUr5PHZw5ErO4Xy2lNh9LkH9vXDb8wc7BOvfSPc0i4xt6I5Qy3jaBLnvg9wPenPoeW0LvQ1x3GtfUm00eNFHdBDd
CLERK_SECRET_KEY=your_clerk_secret_key

# Backend Environment Variables
DATABASE_URL=your_database_url
```

### Docker Commands

```bash
# Navigate to docker directory
cd docker

# Build images
docker build -f Dockerfile.frontend -t photoai-frontend ..
docker build -f Dockerfile.backend -t photoai-backend ..

# Run frontend container
docker run -p 3000:3000 \
  -e NEXT_PUBLIC_CLERK_PUBLISHABLE_KEY=pk_live_Y2xlcmsuMTAweGRldnMuY29tJA \
  -e NEXT_PUBLIC_BACKEND_URL=https://api.photoaiv2.100xdevs.com \
  -e NEXT_PUBLIC_STRIPE_KEY=pk_test_51QsCmFEI53oUr5PHZw5ErO4Xy2lNh9LkH9vXDb8wc7BOvfSPc0i4xt6I5Qy3jaBLnvg9wPenPoeW0LvQ1x3GtfUm00eNFHdBDd \
  -e CLERK_SECRET_KEY=your_clerk_secret_key \
  photoai-frontend

# Run backend container
docker run -p 8080:8080 \
  -e DATABASE_URL=your_database_url \
  photoai-backend
```

## Directory Structure

```
.
├── apps
│   ├── web/                 # Next.js frontend application
│   │   ├── app/            # App router pages and layouts
│   │   ├── components/     # React components
│   │   ├── hooks/          # Custom React hooks
│   │   └── lib/            # Utilities and helpers
│   └── backend/            # Node.js backend service
│       ├── routes/         # API routes
│       ├── services/       # Business logic
│       └── models/         # Data models
├── packages
│   ├── ui/                 # Shared UI components
│   ├── db/                 # Prisma ORM configuration
│   ├── common/             # Shared types and utilities
│   ├── typescript-config/  # Shared TypeScript configuration
│   └── eslint-config/      # Shared ESLint configuration
├── docker/                 # Docker configuration
│   ├── Dockerfile.frontend
│   └── Dockerfile.backend
├── turbo.json             # Turborepo configuration
├── package.json           # Root package configuration
└── bun.lockb             # Bun lock file
```

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the LICENSE file for details


## Develoed By:
G.YUVA KISHORE REDDY

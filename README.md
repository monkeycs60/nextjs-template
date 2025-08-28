# 🚀 Next.js 15 AI-Ready Starter Template

A production-ready Next.js boilerplate with modern stack, strict development standards, and AI-powered development workflow.

[![Next.js 15](https://img.shields.io/badge/Next.js-15.3.3-black?style=flat&logo=next.js)](https://nextjs.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-5-3178C6?style=flat&logo=typescript)](https://typescriptlang.org)
[![Tailwind CSS v4](https://img.shields.io/badge/Tailwind-v4-38B2AC?style=flat&logo=tailwindcss)](https://tailwindcss.com)
[![Prisma](https://img.shields.io/badge/Prisma-6.9-2D3748?style=flat&logo=prisma)](https://prisma.io)
[![Better Auth](https://img.shields.io/badge/Better_Auth-1.2-FF6B35?style=flat)](https://better-auth.com)

## ✨ Features

- 🔥 **Next.js 15** with App Router and Turbopack for blazing fast development
- 🎨 **Tailwind CSS v4** for modern, utility-first styling
- 🔐 **Better Auth** with email/password and Google OAuth
- 🌐 **Internationalization** (French/English) with next-intl
- 📱 **Responsive Design** with shadcn/ui components
- 🛡️ **Type Safety** with strict TypeScript configuration and utils functions
- 🗄️ **Database** with Prisma and PostgreSQL
- 🧪 **E2E Testing** with Playwright
- 🎯 **Form Validation** with React Hook Form and Zod
- 🚦 **Server Actions** with next-safe-action
- 🤖 **AI-Powered Development** with Claude Code integration
- 📊 **State Management** with TanStack Query
- 🎭 **Theming** with next-themes (dark/light mode)


## 🚀 Quick Start

### Prerequisites

- Node.js 18+ 
- PostgreSQL database
- npm/yarn/pnpm

### Installation

1. **Clone and install dependencies:**
```bash
git clone <repository-url>
cd nextjs-template
npm install
```

2. **Set up your database:**
```bash
# Create a PostgreSQL database
createdb your_database_name

# Set up environment variables
cp .env.example .env.local
# Edit .env.local with your database URL and auth secrets
```

3. **Configure environment variables:**
```bash
# Database
DATABASE_URL="postgresql://username:password@localhost:5432/your_database"
SHADOW_DATABASE_URL="postgresql://username:password@localhost:5432/your_shadow_db"

# Auth
BETTER_AUTH_SECRET="your-secret-key"
BETTER_AUTH_URL="http://localhost:3000"

# Google OAuth (optional)
GOOGLE_CLIENT_ID="your-google-client-id"
GOOGLE_CLIENT_SECRET="your-google-client-secret"

# AI Integration (optional)
GOOGLE_GENERATIVE_AI_API_KEY="your-gemini-api-key"
```

4. **Run database migrations:**
```bash
npx prisma migrate dev
npx prisma generate
```

5. **Start development server:**
```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

## 📁 Project Structure

```
├── app/                          # Next.js App Router
│   ├── [locale]/                # Internationalized routes
│   │   ├── components/          # Locale-specific components
│   │   ├── login/              # Authentication pages
│   │   └── profile/            # User profile pages
│   ├── api/                    # API routes
│   ├── globals.css             # Global styles
│   └── layout.tsx              # Root layout
├── components/                  # Reusable components
│   └── ui/                     # shadcn/ui components
├── lib/                        # Utilities and configurations
│   ├── actions/                # Server actions
│   ├── services/               # Database services
│   ├── schemas/                # Validation schemas
│   ├── auth.ts                 # Authentication config
│   └── prisma.ts               # Database client
├── messages/                   # i18n translation files
│   ├── en.json                 # English translations
│   └── fr.json                 # French translations
├── prisma/                     # Database schema and migrations
│   ├── schema.prisma           # Database schema
│   └── migrations/             # Database migrations
├── tests/                      # Test files
│   └── e2e/                    # Playwright E2E tests
└── types/                      # TypeScript type definitions
```

## 🧪 Development Scripts

```bash
# Development
npm run dev              # Start dev server with Turbopack
npm run build            # Build for production
npm run start            # Start production server
npm run lint             # Run ESLint

# Testing
npm run test:e2e         # Run Playwright tests
npm run test:e2e:ui      # Run tests with UI mode
```

## 🤖 AI-Powered Development

This template integrates seamlessly with **Claude Code** for an enhanced development experience:

### Available Agents

- **🔍 laser-lewis** - Code quality enforcement agent
  - Verifies TypeScript strict typing (no `any`)
  - Ensures proper component architecture
  - Checks internationalization compliance
  - Removes unnecessary code and comments

### Development Workflow

1. Write your code following the established patterns
2. Run `laser-lewis` agent for code quality verification
3. Use Playwright MCP for UI testing and debugging
4. All code is automatically checked against strict standards

## 📋 Development Standards

### Prohibited Practices ❌

- **No useEffect** - Use server components for data fetching
- **No TypeScript any** - Strict typing required
- **No OOP patterns** - Functional approach preferred

### Required Practices ✅

- **shadcn/ui components** exclusively
- **Server-first architecture** - Fetch data in page.tsx
- **Type-safe server actions** with next-safe-action
- **Internationalization** for all user-facing text
- **Authentication checks** with `getTypedSession()`

### Code Organization

- **Feature-based architecture** - Group by business domain
- **Component splitting** - Max 350 lines per file
- **Service layer** - All API calls in `lib/services/`
- **Self-documenting code** - Avoid unnecessary comments

## 🗄️ Database

This template uses **Prisma** with **PostgreSQL**:

- User authentication with sessions
- Account linking for OAuth providers

### Key Models

- `User` - User accounts and profiles
- `Session` - Authentication sessions
- `Account` - OAuth provider accounts
- `Verification` - Email verification tokens

## 🌐 Internationalization

Built-in support for multiple languages:

- **Routing** - `/en/...` and `/fr/...` routes
- **Server Components** - `getTranslations()` function
- **Client Components** - `useTranslations()` hook
- **Form Validation** - Translated error messages

## 🧪 Testing

Comprehensive testing setup with **Playwright**:

- E2E authentication flows
- Form validation testing
- Responsive design tests
- Accessibility testing

```bash
# Run all tests
npm run test:e2e

# Run with UI mode
npm run test:e2e:ui
```

## 🚀 Deployment

### Vercel (Recommended)

1. Push to GitHub/GitLab
2. Connect to Vercel
3. Set environment variables
4. Deploy automatically

### Environment Variables for Production

```bash
DATABASE_URL="your-production-db-url"
BETTER_AUTH_SECRET="secure-random-string"
BETTER_AUTH_URL="https://your-domain.com"
```

## 🤝 Contributing

1. Follow the established code standards
2. Run `laser-lewis` agent before committing
3. Ensure all tests pass with Playwright
4. Add translations for new user-facing text

## 📚 Learn More

- [Next.js Documentation](https://nextjs.org/docs)
- [Better Auth Docs](https://better-auth.com)
- [shadcn/ui Components](https://ui.shadcn.com)
- [Prisma Documentation](https://prisma.io/docs)
- [next-intl Guide](https://next-intl-docs.vercel.app)
- [Playwright Testing](https://playwright.dev)

## 📄 License

This template is open source and available under the [MIT License](LICENSE).

---

**Built by Clément Serizay with ❤️ for modern web development**

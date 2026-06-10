# Reels Pro

A full-stack short-form video ("reels") platform built with Next.js. It handles
user authentication, video uploads, and optimized video delivery through
ImageKit, with data persisted in MongoDB.

## Features

- 🔐 Email/password authentication with [NextAuth.js](https://authjs.dev/) and bcrypt-hashed passwords
- 📹 Video upload and delivery via [ImageKit](https://imagekit.io/), tuned for 1080×1920 vertical reels
- 🛡️ Route protection through Next.js middleware
- 🗄️ MongoDB persistence with Mongoose models and connection caching
- 🎨 Styled with Tailwind CSS v4
- ⚡ Built on the Next.js App Router with TypeScript

## Tech Stack

| Layer          | Technology                          |
| -------------- | ----------------------------------- |
| Framework      | Next.js 16 (App Router), React 19   |
| Language       | TypeScript                          |
| Auth           | NextAuth.js v5                      |
| Database       | MongoDB + Mongoose                  |
| Media          | ImageKit                            |
| Styling        | Tailwind CSS v4                     |

## Getting Started

### Prerequisites

- Node.js 20+
- A MongoDB database (local or Atlas)
- An [ImageKit](https://imagekit.io/) account

### Installation

```bash
pnpm install
```

### Environment Variables

Create a `.env.local` file in the project root:

```bash
# MongoDB
MONGODB_URI=your_mongodb_connection_string

# NextAuth
NEXTAUTH_SECRET=your_nextauth_secret
NEXTAUTH_URL=http://localhost:3000

# ImageKit
NEXT_PUBLIC_PUBLIC_KEY=your_imagekit_public_key
PRIVATE_KEY=your_imagekit_private_key
NEXT_PUBLIC_URL_ENDPOINT=your_imagekit_url_endpoint
```

### Development

```bash
pnpm dev
```

Open [http://localhost:3000](http://localhost:3000) to view the app.

### Build

```bash
pnpm build
pnpm start
```

## Project Structure

```
app/
  api/
    auth/[...nextauth]/   NextAuth route handler
    auth/register/        User registration endpoint
    imagekit-auth/        ImageKit auth params endpoint
  layout.tsx
  page.tsx
lib/
  auth.ts                NextAuth configuration
  db.ts                  Cached MongoDB connection
models/
  User.ts                User schema (bcrypt password hashing)
  Video.ts               Video schema
middleware.ts            Route protection
```

## License

This project is licensed under the [MIT License](./LICENSE).

# 🤖 Agents API

Agents API is a backend service for an AI-assisted classroom Q&A application. Users can create and access rooms, upload class audio, store transcriptions with vector embeddings, and ask questions that are answered from the most relevant parts of the recorded class content.

## 🚀 Technologies

- **Node.js** with native TypeScript support (experimental strip types)
- **Fastify** - Fast and efficient web framework
- **PostgreSQL** with the **pgvector** extension for vector storage
- **Drizzle ORM** - Type-safe database operations
- **Zod** - Schema validation
- **Docker** - Database containerization
- **Biome** - Code linting and formatting

## 🏗️ Architecture

The project follows a modular architecture with:

- **Separation of concerns** between routes, schemas, services, and database connection
- **Schema validation** with Zod for type safety
- **Type-safe ORM** with Drizzle for database operations
- **Centralized environment variable validation**
- **AI services** isolated from HTTP route handlers

## ⚙️ Setup and Configuration

### Prerequisites

- Node.js with support for `--experimental-strip-types`
- Docker and Docker Compose

### 1. Clone the repository

```bash
git clone <repository-url>
cd server
```

### 2. Start the database

```bash
docker-compose up -d
```

### 3. Configure environment variables

Create a `.env` file in the project root:

```env
PORT=3333
DATABASE_URL=postgresql://docker:docker@localhost:5432/agents
GEMINI_API_KEY=your-google-ai-studio-api-key
```

### 4. Install dependencies

```bash
npm install
```

### 5. Run database migrations

```bash
npx drizzle-kit migrate
```

### 6. (Optional) Seed the database with sample data

```bash
npm run db:seed
```

### 7. Run the project

**Development:**

```bash
npm run dev
```

**Production:**

```bash
npm start
```

## 📚 Available Scripts

- `npm run dev` - Runs the server in development mode with hot reload
- `npm start` - Runs the server in production mode
- `npm run db:seed` - Seeds the database with sample data

## 🌐 Endpoints

The API will be available at `http://localhost:3333`

- `GET /health` - Application health check
- `GET /rooms` - Lists available rooms

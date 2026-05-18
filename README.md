# Memory Palace Chat

**Memory Palace Chat** is an immersive, evolving 3D communication platform. Every message sent is transformed into a floating origami object that drifts into a shared, persistent 3D room. As the conversation progresses, the AI "architect" shapes, stacks, and repaints these objects, turning your chat history into a glowing, labyrinthine museum of thoughts.

---

## 🏗️ Architecture Overview
The system follows a monorepo architecture, utilizing a decoupled approach between the 3D rendering engine and the data persistence layer.

*   **Frontend:** A React-based SPA utilizing **React-Three-Fiber** for WebGL rendering, with state synchronized via **Zustand**.
*   **Backend:** An **Express.js** API that handles authentication, AI transformation logic, and spatial object persistence.
*   **Real-time:** **Socket.io** manages real-time updates, allowing multiple users to see the palace evolve simultaneously.
*   **Database:** **PostgreSQL** (with PostGIS) stores the spatial metadata (x, y, z coordinates) and message history.

---

## 🛠️ Technology Stack

| Layer | Technology |
| :--- | :--- |
| **Frontend** | React, Three.js, React-Three-Fiber, Tailwind CSS |
| **Backend** | Node.js, Express.js, Socket.io |
| **Database** | PostgreSQL, Prisma ORM |
| **Deployment** | Vercel, GitHub Actions |

---

## 📊 Project Summary
*   **Total Phases:** 7
*   **Total Issues:** 35
*   **Core Philosophy:** Transform ephemeral chat into permanent, navigable spatial memory.

---

## 🚀 Development Phases

1.  **Infrastructure Setup:** Monorepo configuration (Turborepo), DB schema definition, and CI/CD pipelines.
2.  **Backend Foundations:** JWT authentication, spatial CRUD, AI transformation services, and message threading.
3.  **3D Scene Foundation:** R3F Canvas, Origami Mesh components, and interaction logic (raycasting).
4.  **Integration Layer:** Bridging the Socket.io real-time stream with the frontend state and API service layer.
5.  **Testing & Quality:** Comprehensive unit, integration, and performance stress-testing.
6.  **Deployment:** Vercel production configuration, automated migrations, and monitoring (Sentry).
7.  **Documentation:** OpenAPI/Swagger specs, architecture diagrams, and contribution guidelines.

---

## 🏁 Getting Started

### Prerequisites
*   Node.js (v18+)
*   PostgreSQL
*   Turborepo (`npm install turbo --global`)

### Local Installation
1. **Clone the repository:**
   ```bash
   git clone <repo-url>
   cd memory-palace-chat
   ```
2. **Install dependencies:**
   ```bash
   npm install
   ```
3. **Environment Setup:**
   Copy the `.env.example` files in both `apps/web` and `apps/api` to `.env` and fill in your local database credentials and API keys.
4. **Database Migration:**
   ```bash
   npx prisma migrate dev
   ```
5. **Start Development:**
   ```bash
   turbo run dev
   ```

---

## 📝 Implementation Notes
*   **Spatial Logic:** Origami coordinates are stored as floats. Use the `SPATIAL-002` proximity query logic to ensure the scene remains performant as it grows.
*   **AI Transformation:** The AI service is decoupled. Use the `AI-002` Redis caching layer to minimize latency and API costs.
*   **Performance:** For large conversations, rely on the `MPC-029` InstancedMesh implementation to maintain a steady 60fps.
*   **Security:** Always ensure `JWT_SECRET` is rotated in production via Vercel’s encrypted environment variables.

---

*This project is built to turn conversations into architecture. Happy building.*
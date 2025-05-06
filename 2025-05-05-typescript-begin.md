# 📅 Day 1 - 2025-05-05 - TypeScript Begin

## 📚 What I Learned Today

- **What is Node.js?**  
  Node.js is a lightweight runtime that allows JavaScript to run outside the browser, such as on a computer or server.  
  Unlike Java (which is multi-threaded), Node.js uses a single-threaded, event-driven architecture.  
  This makes it well-suited for high-concurrency scenarios like real-time systems, chats, or games.

- **`tsc --init`**  
  This command generates a `tsconfig.json` file, which configures how TypeScript should compile your code.

- **`tsconfig.json`**  
  A configuration file that controls:
  - Target JS version (e.g., `es2016`)
  - Module system (e.g., `commonjs`)
  - Strict type checks
  - JSON module resolution, and more

- **`package-lock.json`**  
  Ensures consistent dependency versions across all developers in the team.  
  `npm` installs based on `package-lock.json` first, then falls back to `package.json` if necessary.

- **`express` vs Spring Boot**  
  In Node.js, `express` is similar to `@SpringBootApplication` in Java — it starts the server and defines API routes.  
  It’s minimalist, giving more control but requiring you to assemble the building blocks yourself.

---

## 🧱 Full Flow of a RESTful API in Node.js

**Structure:**

| Layer     | Responsibility                  |
|-----------|----------------------------------|
| `Controller` | Handles HTTP requests (`req`, `res`) |
| `Service`    | Contains core business logic        |
| `Route`      | Maps API paths to controller methods |
| `index.js`   | Entry point, activates routing and starts server |

---

### 🔧 Sample Code

```ts
// index.ts

import express from "express";
import userRoutes from "./src/routes/user.routes";

const app = express();

// Enables parsing of JSON request bodies
app.use(express.json());

// Mount user-related routes under /users path
app.use("/users", userRoutes);

// Start the server
app.listen(3000, () => {
  console.log("Server is running at http://localhost:3000");
});

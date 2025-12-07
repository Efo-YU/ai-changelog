
## 2025-12-07 - chore: Add MIT license file

This commit introduces the MIT License, copyright 2025 Efo, ensuring clear licensing terms for the project.

<details>
<summary>📄 Click to view raw diff</summary>

```diff
diff --git a/LICENSE b/LICENSE
new file mode 100644
index 0000000..7e350c4
--- /dev/null
+++ b/LICENSE
@@ -0,0 +1,21 @@
+MIT License
+
+Copyright (c) 2025 Efo
+
+Permission is hereby granted, free of charge, to any person obtaining a copy
+of this software and associated documentation files (the "Software"), to deal
+in the Software without restriction, including without limitation the rights
+to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
+copies of the Software, and to permit persons to whom the Software is
+furnished to do so, subject to the following conditions:
+
+The above copyright notice and this permission notice shall be included in all
+copies or substantial portions of the Software.
+
+THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
+IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
+FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
+AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
+LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
+OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
+SOFTWARE.
```
</details>
---

## 2025-12-07 - feat: Add modern SPA demo component for logging tests

Introduces junks-for-logging-demo/ModernSpa.tsx, a self-contained React component using Tailwind CSS styling (v4 theme) and basic React state (useState) to serve as a target for logging and instrumentation demonstrations.

<details>
<summary>📄 Click to view raw diff</summary>

```diff
diff --git a/junks-for-logging-demo/ModernSpa.tsx b/junks-for-logging-demo/ModernSpa.tsx
new file mode 100644
index 0000000..7227aba
--- /dev/null
+++ b/junks-for-logging-demo/ModernSpa.tsx
@@ -0,0 +1,55 @@
+import { useState } from "react";
+
+function App() {
+  const [count, setCount] = useState(0);
+
+  return (
+    <div className="min-h-screen flex items-center justify-center bg-gray-950 p-4">
+      <div className="max-w-md w-full bg-gray-900 border border-gray-800 rounded-2xl shadow-2xl overflow-hidden">
+        {/* Header Image Area */}
+        <div className="h-32 bg-gradient-to-r from-indigo-500 via-purple-500 to-pink-500 flex items-center justify-center">
+          <span className="text-white/90 font-bold text-3xl tracking-widest drop-shadow-md">
+            V4
+          </span>
+        </div>
+
+        {/* Content Area */}
+        <div className="p-8 space-y-6">
+          <div className="text-center space-y-2">
+            <h1 className="text-2xl font-bold text-white tracking-tight">
+              Tailwind CSS v4
+            </h1>
+            <p className="text-gray-400">
+              Zero configuration, lightning fast build times, and a new
+              CSS-first configuration engine.
+            </p>
+          </div>
+
+          {/* Interactive Elements */}
+          <div className="flex flex-col gap-3">
+            <button
+              onClick={() => setCount((c) => c + 1)}
+              className="cursor-pointer w-full py-2.5 px-4 bg-white text-gray-900 font-semibold rounded-lg hover:bg-gray-100 active:scale-95 transition-all duration-200"
+            >
+              Count is {count}
+            </button>
+
+            <button className="cursor-pointer w-full py-2.5 px-4 bg-gray-800 text-gray-300 font-medium rounded-lg border border-gray-700 hover:bg-gray-700 hover:text-white transition-colors">
+              Documentation
+            </button>
+          </div>
+        </div>
+
+        {/* Footer */}
+        <div className="bg-gray-950/50 p-4 text-center border-t border-gray-800">
+          <p className="text-xs text-gray-500">
+            Edit <code className="text-indigo-400 font-mono">src/App.tsx</code>{" "}
+            to start.
+          </p>
+        </div>
+      </div>
+    </div>
+  );
+}
+
+export default App;
```
</details>
---

## 2025-12-07 - chore: Add pure HTML/JS hash routing SPA demo file

Introduces `pureHtmlSpa.html` to the `junks-for-logging-demo` directory. This file is a self-contained Single Page Application (SPA) built purely with HTML, CSS, and vanilla JavaScript using hash routing. It includes basic styling, navigation logic, and different views ('home', 'about', 'contact') for demonstration purposes. This asset is useful for logging, performance testing, or integration demos where a simple, framework-less frontend environment is required.

<details>
<summary>📄 Click to view raw diff</summary>

```diff
diff --git a/junks-for-logging-demo/pureHtmlSpa.html b/junks-for-logging-demo/pureHtmlSpa.html
new file mode 100644
index 0000000..3b5a213
--- /dev/null
+++ b/junks-for-logging-demo/pureHtmlSpa.html
@@ -0,0 +1,240 @@
+<!DOCTYPE html>
+<html lang="en">
+  <head>
+    <meta charset="UTF-8" />
+    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
+    <title>Pure JS SPA</title>
+    <style>
+      /* --- CSS Reset & Variables --- */
+      :root {
+        --primary-color: #3b82f6;
+        --text-color: #333;
+        --bg-color: #f4f4f9;
+        --nav-bg: #ffffff;
+      }
+
+      * {
+        box-sizing: border-box;
+        margin: 0;
+        padding: 0;
+      }
+
+      body {
+        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
+          Helvetica, Arial, sans-serif;
+        background-color: var(--bg-color);
+        color: var(--text-color);
+        line-height: 1.6;
+        display: flex;
+        flex-direction: column;
+        min-height: 100vh;
+      }
+
+      /* --- Navigation --- */
+      header {
+        background-color: var(--nav-bg);
+        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
+        position: sticky;
+        top: 0;
+      }
+
+      nav {
+        max-width: 800px;
+        margin: 0 auto;
+        padding: 1rem;
+        display: flex;
+        justify-content: space-between;
+        align-items: center;
+      }
+
+      .logo {
+        font-weight: bold;
+        font-size: 1.5rem;
+        color: var(--primary-color);
+        text-decoration: none;
+      }
+
+      .nav-links a {
+        text-decoration: none;
+        color: var(--text-color);
+        margin-left: 20px;
+        font-weight: 500;
+        transition: color 0.3s;
+      }
+
+      .nav-links a:hover,
+      .nav-links a.active {
+        color: var(--primary-color);
+      }
+
+      /* --- Main Content Area --- */
+      main {
+        flex: 1;
+        max-width: 800px;
+        width: 100%;
+        margin: 2rem auto;
+        padding: 0 1rem;
+        animation: fadeIn 0.5s ease-in-out;
+      }
+
+      /* --- Dynamic View Styles --- */
+      .card {
+        background: white;
+        padding: 2rem;
+        border-radius: 8px;
+        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
+      }
+
+      h1 {
+        margin-bottom: 1rem;
+      }
+      p {
+        margin-bottom: 1rem;
+      }
+
+      button {
+        background-color: var(--primary-color);
+        color: white;
+        border: none;
+        padding: 10px 20px;
+        border-radius: 5px;
+        cursor: pointer;
+        font-size: 1rem;
+      }
+
+      button:hover {
+        opacity: 0.9;
+      }
+
+      /* --- Footer --- */
+      footer {
+        text-align: center;
+        padding: 1rem;
+        background-color: var(--nav-bg);
+        border-top: 1px solid #ddd;
+        font-size: 0.9rem;
+        color: #666;
+      }
+
+      /* --- Animations --- */
+      @keyframes fadeIn {
+        from {
+          opacity: 0;
+          transform: translateY(10px);
+        }
+        to {
+          opacity: 1;
+          transform: translateY(0);
+        }
+      }
+    </style>
+  </head>
+  <body>
+    <header>
+      <nav>
+        <a href="#home" class="logo">PureSPA</a>
+        <div class="nav-links">
+          <a href="#home" data-link>Home</a>
+          <a href="#about" data-link>About</a>
+          <a href="#contact" data-link>Contact</a>
+        </div>
+      </nav>
+    </header>
+
+    <main id="app"></main>
+
+    <footer>
+      <p>&copy; 2023 Pure HTML/JS SPA. No Frameworks.</p>
+    </footer>
+
+    <script>
+      // --- 1. Define Routes & Content ---
+      // In a real app, this might fetch HTML templates from a server.
+      const routes = {
+        home: `
+                <div class="card">
+                    <h1>Welcome Home 🏠</h1>
+                    <p>This is a single page application built without React, Vue, or Angular.</p>
+                    <p>It uses <strong>Hash Routing</strong> to switch content without reloading the page.</p>
+                    <button onclick="window.location.hash = '#about'">Go to About</button>
+                </div>
+            `,
+        about: `
+                <div class="card">
+                    <h1>About Us 📖</h1>
+                    <p>We believe in the power of vanilla JavaScript.</p>
+                    <p>SPAs work by intercepting navigation and swapping the HTML inside a main container div.</p>
+                    <ul>
+                        <li>Fast navigation</li>
+                        <li>No page reloads</li>
+                        <li>Clean architecture</li>
+                    </ul>
+                </div>
+            `,
+        contact: `
+                <div class="card">
+                    <h1>Contact ✉️</h1>
+                    <p>Want to get in touch? This form does nothing, but it looks nice!</p>
+                    <form onsubmit="event.preventDefault(); alert('Message sent (hypothetically)!')">
+                        <div style="margin-bottom: 10px;">
+                            <label style="display:block; margin-bottom:5px">Email</label>
+                            <input type="email" placeholder="you@example.com" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px;" required>
+                        </div>
+                        <div style="margin-bottom: 10px;">
+                            <label style="display:block; margin-bottom:5px">Message</label>
+                            <textarea rows="3" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px;"></textarea>
+                        </div>
+                        <button type="submit">Send Message</button>
+                    </form>
+                </div>
+            `,
+        404: `
+                <div class="card" style="text-align: center; color: #d32f2f;">
+                    <h1>404 Not Found</h1>
+                    <p>Oops! The page you are looking for doesn't exist.</p>
+                    <a href="#home" style="color: var(--primary-color);">Go back home</a>
+                </div>
+            `,
+      };
+
+      // --- 2. The Router Function ---
+      function router() {
+        // Get the current hash (remove the # symbol). Default to 'home'.
+        let hash = window.location.hash.slice(1) || "home";
+
+        // Resolve the route. If it doesn't exist, use 404.
+        const content = routes[hash] || routes["404"];
+
+        // Inject content into the DOM
+        const app = document.getElementById("app");
+        app.innerHTML = content;
+
+        // Re-trigger animation by removing and adding the element (optional polish)
+        app.style.animation = "none";
+        app.offsetHeight; /* trigger reflow */
+        app.style.animation = null;
+
+        updateActiveNav(hash);
+      }
+
+      // --- 3. Update Active Navigation State ---
+      function updateActiveNav(hash) {
+        document.querySelectorAll(".nav-links a").forEach((link) => {
+          const linkHref = link.getAttribute("href").slice(1);
+          if (linkHref === hash) {
+            link.classList.add("active");
+          } else {
+            link.classList.remove("active");
+          }
+        });
+      }
+
+      // --- 4. Event Listeners ---
+      // Listen for hash changes (when user clicks links or back/forward buttons)
+      window.addEventListener("hashchange", router);
+
+      // Load the correct route when the page first loads
+      window.addEventListener("load", router);
+    </script>
+  </body>
+</html>
```
</details>
---

## 2025-12-07 - feat: Implement advanced SPA features (API, State, Dark Mode)
> ⚠️ **BREAKING CHANGE**

Overhaul the pure JavaScript SPA demo to showcase advanced vanilla JS techniques:
- Introduced global state management (posts, saved items).
- Implemented asynchronous routing with dynamic data fetching from an external API (JSONPlaceholder).
- Added modern CSS design, including full dark mode support via CSS variables and persistent storage (localStorage).
- Replaced static HTML route strings with modular, async view functions, transforming the entire application architecture.

<details>
<summary>📄 Click to view raw diff</summary>

```diff
diff --git a/junks-for-logging-demo/pureHtmlSpa.html b/junks-for-logging-demo/pureHtmlSpa.html
index 3b5a213..c18d178 100644
--- a/junks-for-logging-demo/pureHtmlSpa.html
+++ b/junks-for-logging-demo/pureHtmlSpa.html
@@ -3,14 +3,28 @@
   <head>
     <meta charset="UTF-8" />
     <meta name="viewport" content="width=device-width, initial-scale=1.0" />
-    <title>Pure JS SPA</title>
+    <title>Advanced Pure SPA</title>
     <style>
-      /* --- CSS Reset & Variables --- */
+      /* --- CSS Variables & Dark Mode --- */
       :root {
-        --primary-color: #3b82f6;
-        --text-color: #333;
-        --bg-color: #f4f4f9;
-        --nav-bg: #ffffff;
+        --primary: #6366f1;
+        --bg: #f8fafc;
+        --card-bg: #ffffff;
+        --text: #1e293b;
+        --text-muted: #64748b;
+        --border: #e2e8f0;
+        --nav-bg: rgba(255, 255, 255, 0.9);
+      }
+
+      /* Dark Theme Class */
+      body.dark-mode {
+        --primary: #818cf8;
+        --bg: #0f172a;
+        --card-bg: #1e293b;
+        --text: #f1f5f9;
+        --text-muted: #94a3b8;
+        --border: #334155;
+        --nav-bg: rgba(30, 41, 59, 0.9);
       }
 
       * {
@@ -20,26 +34,25 @@
       }
 
       body {
-        font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto,
-          Helvetica, Arial, sans-serif;
-        background-color: var(--bg-color);
-        color: var(--text-color);
-        line-height: 1.6;
-        display: flex;
-        flex-direction: column;
-        min-height: 100vh;
+        font-family: "Segoe UI", sans-serif;
+        background-color: var(--bg);
+        color: var(--text);
+        transition: background 0.3s, color 0.3s;
+        padding-bottom: 50px;
       }
 
       /* --- Navigation --- */
       header {
-        background-color: var(--nav-bg);
-        box-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
         position: sticky;
         top: 0;
+        background: var(--nav-bg);
+        backdrop-filter: blur(10px);
+        border-bottom: 1px solid var(--border);
+        z-index: 100;
       }
 
       nav {
-        max-width: 800px;
+        max-width: 900px;
         margin: 0 auto;
         padding: 1rem;
         display: flex;
@@ -48,83 +61,117 @@
       }
 
       .logo {
-        font-weight: bold;
-        font-size: 1.5rem;
-        color: var(--primary-color);
+        font-weight: 800;
+        font-size: 1.25rem;
+        color: var(--primary);
         text-decoration: none;
       }
 
+      .nav-links {
+        display: flex;
+        gap: 20px;
+        align-items: center;
+      }
+
       .nav-links a {
         text-decoration: none;
-        color: var(--text-color);
-        margin-left: 20px;
-        font-weight: 500;
-        transition: color 0.3s;
+        color: var(--text-muted);
+        font-weight: 600;
+        transition: color 0.2s;
       }
 
       .nav-links a:hover,
       .nav-links a.active {
-        color: var(--primary-color);
+        color: var(--primary);
       }
 
-      /* --- Main Content Area --- */
+      /* Theme Toggle Button */
+      .theme-btn {
+        background: none;
+        border: 1px solid var(--border);
+        color: var(--text);
+        padding: 5px 10px;
+        border-radius: 20px;
+        cursor: pointer;
+        font-size: 0.8rem;
+      }
+
+      /* --- Layout & Grid --- */
       main {
-        flex: 1;
-        max-width: 800px;
-        width: 100%;
+        max-width: 900px;
         margin: 2rem auto;
         padding: 0 1rem;
-        animation: fadeIn 0.5s ease-in-out;
       }
 
-      /* --- Dynamic View Styles --- */
+      .grid {
+        display: grid;
+        grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
+        gap: 1.5rem;
+      }
+
+      /* --- Cards --- */
       .card {
-        background: white;
-        padding: 2rem;
-        border-radius: 8px;
-        box-shadow: 0 2px 5px rgba(0, 0, 0, 0.05);
+        background: var(--card-bg);
+        border: 1px solid var(--border);
+        border-radius: 12px;
+        padding: 1.5rem;
+        transition: transform 0.2s;
+        display: flex;
+        flex-direction: column;
+        justify-content: space-between;
       }
 
-      h1 {
-        margin-bottom: 1rem;
+      .card:hover {
+        transform: translateY(-2px);
+        border-color: var(--primary);
+      }
+
+      h2 {
+        font-size: 1.1rem;
+        margin-bottom: 0.5rem;
       }
       p {
+        color: var(--text-muted);
+        font-size: 0.9rem;
         margin-bottom: 1rem;
       }
 
-      button {
-        background-color: var(--primary-color);
+      /* --- Buttons --- */
+      .btn {
+        background-color: var(--primary);
         color: white;
         border: none;
-        padding: 10px 20px;
-        border-radius: 5px;
+        padding: 8px 16px;
+        border-radius: 6px;
         cursor: pointer;
-        font-size: 1rem;
+        font-size: 0.9rem;
+        align-self: flex-start;
       }
-
-      button:hover {
-        opacity: 0.9;
+      .btn.outline {
+        background: transparent;
+        border: 1px solid var(--primary);
+        color: var(--primary);
       }
-
-      /* --- Footer --- */
-      footer {
-        text-align: center;
-        padding: 1rem;
-        background-color: var(--nav-bg);
-        border-top: 1px solid #ddd;
-        font-size: 0.9rem;
-        color: #666;
+      .btn:active {
+        transform: scale(0.98);
       }
 
-      /* --- Animations --- */
-      @keyframes fadeIn {
-        from {
-          opacity: 0;
-          transform: translateY(10px);
+      /* --- Loading Spinner --- */
+      .spinner {
+        border: 4px solid var(--border);
+        border-top: 4px solid var(--primary);
+        border-radius: 50%;
+        width: 40px;
+        height: 40px;
+        animation: spin 1s linear infinite;
+        margin: 50px auto;
+      }
+      @keyframes spin {
+        0% {
+          transform: rotate(0deg);
         }
-        to {
-          opacity: 1;
-          transform: translateY(0);
+        100% {
+          transform: rotate(360deg);
         }
       }
     </style>
@@ -132,109 +179,177 @@
   <body>
     <header>
       <nav>
-        <a href="#home" class="logo">PureSPA</a>
+        <a href="#home" class="logo">PureSPA Pro</a>
         <div class="nav-links">
           <a href="#home" data-link>Home</a>
-          <a href="#about" data-link>About</a>
-          <a href="#contact" data-link>Contact</a>
+          <a href="#posts" data-link>Posts (API)</a>
+          <a href="#saved" data-link>Saved (<span id="saved-count">0</span>)</a>
+          <button class="theme-btn" onclick="toggleTheme()">🌓 Theme</button>
         </div>
       </nav>
     </header>
 
     <main id="app"></main>
 
-    <footer>
-      <p>&copy; 2023 Pure HTML/JS SPA. No Frameworks.</p>
-    </footer>
-
     <script>
-      // --- 1. Define Routes & Content ---
-      // In a real app, this might fetch HTML templates from a server.
-      const routes = {
-        home: `
-                <div class="card">
-                    <h1>Welcome Home 🏠</h1>
-                    <p>This is a single page application built without React, Vue, or Angular.</p>
-                    <p>It uses <strong>Hash Routing</strong> to switch content without reloading the page.</p>
-                    <button onclick="window.location.hash = '#about'">Go to About</button>
-                </div>
-            `,
-        about: `
-                <div class="card">
-                    <h1>About Us 📖</h1>
-                    <p>We believe in the power of vanilla JavaScript.</p>
-                    <p>SPAs work by intercepting navigation and swapping the HTML inside a main container div.</p>
-                    <ul>
-                        <li>Fast navigation</li>
-                        <li>No page reloads</li>
-                        <li>Clean architecture</li>
-                    </ul>
+      // --- 1. STATE MANAGEMENT ---
+      const state = {
+        posts: [], // Will store data fetched from API
+        savedIds: new Set(), // Will store IDs of favorites
+        hasFetched: false,
+      };
+
+      // --- 2. HELPERS ---
+
+      // Dark Mode Logic
+      function initTheme() {
+        const savedTheme = localStorage.getItem("theme");
+        if (savedTheme === "dark") document.body.classList.add("dark-mode");
+      }
+
+      function toggleTheme() {
+        document.body.classList.toggle("dark-mode");
+        const isDark = document.body.classList.contains("dark-mode");
+        localStorage.setItem("theme", isDark ? "dark" : "light");
+      }
+
+      // --- 3. VIEW FUNCTIONS (Components) ---
+      // Instead of static strings, we use functions that return HTML strings.
+
+      const Views = {
+        home: async () => `
+                <div style="text-align:center; padding: 40px 20px;">
+                    <h1 style="font-size: 2.5rem; margin-bottom: 1rem; color: var(--primary);">Pure JS Features</h1>
+                    <p style="font-size: 1.1rem; max-width: 600px; margin: 0 auto 30px;">
+                        This example demonstrates <strong>Async Data Fetching</strong>, 
+                        <strong>Global State Management</strong>, and <strong>Theme Toggling</strong> 
+                        without a single library.
+                    </p>
+                    <a href="#posts" class="btn" style="text-decoration:none; font-size: 1.1rem;">Browse Posts via API &rarr;</a>
                 </div>
             `,
-        contact: `
-                <div class="card">
-                    <h1>Contact ✉️</h1>
-                    <p>Want to get in touch? This form does nothing, but it looks nice!</p>
-                    <form onsubmit="event.preventDefault(); alert('Message sent (hypothetically)!')">
-                        <div style="margin-bottom: 10px;">
-                            <label style="display:block; margin-bottom:5px">Email</label>
-                            <input type="email" placeholder="you@example.com" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px;" required>
+
+        posts: async () => {
+          // If we haven't fetched data yet, fetch it now.
+          if (!state.hasFetched) {
+            try {
+              const res = await fetch(
+                "https://jsonplaceholder.typicode.com/posts?_limit=12"
+              );
+              state.posts = await res.json();
+              state.hasFetched = true;
+            } catch (e) {
+              return `<p>Error loading posts.</p>`;
+            }
+          }
+
+          // Generate HTML for the grid
+          const postsHtml = state.posts
+            .map((post) => {
+              const isSaved = state.savedIds.has(post.id);
+              return `
+                    <div class="card">
+                        <div>
+                            <h2>${post.title.substring(0, 30)}...</h2>
+                            <p>${post.body.substring(0, 100)}...</p>
                         </div>
-                        <div style="margin-bottom: 10px;">
-                            <label style="display:block; margin-bottom:5px">Message</label>
-                            <textarea rows="3" style="width: 100%; padding: 8px; border: 1px solid #ccc; border-radius: 4px;"></textarea>
+                        <button 
+                            class="btn ${isSaved ? "outline" : ""}" 
+                            onclick="toggleSave(${post.id})">
+                            ${isSaved ? "Remove Saved" : "♥ Save Post"}
+                        </button>
+                    </div>`;
+            })
+            .join("");
+
+          return `
+                    <div style="margin-bottom: 20px;">
+                        <h1>Latest Posts</h1>
+                        <p>Fetched from JSONPlaceholder API.</p>
+                    </div>
+                    <div class="grid">${postsHtml}</div>
+                `;
+        },
+
+        saved: async () => {
+          // Filter the global posts array by saved IDs
+          const savedPosts = state.posts.filter((p) =>
+            state.savedIds.has(p.id)
+          );
+
+          if (savedPosts.length === 0) {
+            return `
+                        <div style="text-align: center; margin-top: 50px;">
+                            <h2>No saved items yet.</h2>
+                            <p>Go to the <a href="#posts" style="color:var(--primary)">Posts</a> page to add some!</p>
                         </div>
-                        <button type="submit">Send Message</button>
-                    </form>
-                </div>
-            `,
-        404: `
-                <div class="card" style="text-align: center; color: #d32f2f;">
-                    <h1>404 Not Found</h1>
-                    <p>Oops! The page you are looking for doesn't exist.</p>
-                    <a href="#home" style="color: var(--primary-color);">Go back home</a>
-                </div>
-            `,
-      };
+                    `;
+          }
 
-      // --- 2. The Router Function ---
-      function router() {
-        // Get the current hash (remove the # symbol). Default to 'home'.
-        let hash = window.location.hash.slice(1) || "home";
+          const html = savedPosts
+            .map(
+              (post) => `
+                    <div class="card">
+                        <h2>${post.title}</h2>
+                        <button class="btn outline" onclick="toggleSave(${post.id})">Remove</button>
+                    </div>
+                `
+            )
+            .join("");
 
-        // Resolve the route. If it doesn't exist, use 404.
-        const content = routes[hash] || routes["404"];
+          return `
+                    <h1>Your Saved Collection</h1>
+                    <div class="grid" style="margin-top:20px;">${html}</div>
+                `;
+        },
+      };
 
-        // Inject content into the DOM
-        const app = document.getElementById("app");
-        app.innerHTML = content;
+      // --- 4. ACTIONS (Event Handlers) ---
 
-        // Re-trigger animation by removing and adding the element (optional polish)
-        app.style.animation = "none";
-        app.offsetHeight; /* trigger reflow */
-        app.style.animation = null;
+      // We attach this to window so the HTML onclick="" strings can find it
+      window.toggleSave = function (id) {
+        if (state.savedIds.has(id)) {
+          state.savedIds.delete(id);
+        } else {
+          state.savedIds.add(id);
+        }
+        updateSavedCount();
+        router(); // Re-render current page to update button styles
+      };
 
-        updateActiveNav(hash);
+      function updateSavedCount() {
+        document.getElementById("saved-count").innerText = state.savedIds.size;
       }
 
-      // --- 3. Update Active Navigation State ---
-      function updateActiveNav(hash) {
-        document.querySelectorAll(".nav-links a").forEach((link) => {
-          const linkHref = link.getAttribute("href").slice(1);
-          if (linkHref === hash) {
-            link.classList.add("active");
-          } else {
-            link.classList.remove("active");
-          }
+      // --- 5. ROUTER ---
+
+      async function router() {
+        const app = document.getElementById("app");
+        let hash = window.location.hash.slice(1) || "home";
+
+        // Highlight Nav
+        document.querySelectorAll(".nav-links a").forEach((el) => {
+          el.classList.toggle("active", el.getAttribute("href") === `#${hash}`);
         });
+
+        // 1. Show Loading Spinner (if async takes time)
+        if (hash === "posts" && !state.hasFetched) {
+          app.innerHTML = '<div class="spinner"></div>';
+        }
+
+        // 2. Get View Function
+        const viewFn = Views[hash] || Views["home"];
+
+        // 3. Render
+        app.innerHTML = await viewFn();
       }
 
-      // --- 4. Event Listeners ---
-      // Listen for hash changes (when user clicks links or back/forward buttons)
+      // --- 6. INIT ---
       window.addEventListener("hashchange", router);
-
-      // Load the correct route when the page first loads
-      window.addEventListener("load", router);
+      window.addEventListener("load", () => {
+        initTheme();
+        router();
+      });
     </script>
   </body>
 </html>
```
</details>
---

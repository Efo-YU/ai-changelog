
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


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

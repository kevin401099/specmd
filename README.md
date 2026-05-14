what # 🚀 A Beginner's Guide to Specify

Welcome! This guide will teach you how to use **Specify**, a powerful way to turn your ideas into high-quality code. 

Think of Specify as a bridge:
- **Idea** ➡️ **Specification** (What do we want?)
- **Specification** ➡️ **Plan** (How will we build it?)
- **Plan** ➡️ **Tasks** (What steps do we take?)
- **Tasks** ➡️ **Code** (Let's build it!)

---

## 📂 Keeping Things Organized
Specify keeps your **thinking** (Specs) separate from your **doing** (Code).

- **`specs/`**: This folder contains all the "brain work"—descriptions, diagrams, and plans.
- **`src/`**: This folder contains your actual code (Python, JavaScript, etc.).

This separation makes it easy to understand the "Why" and "What" without getting lost in the "How".

---

## 🛠 The 3-Step Workflow (Plus 3 Optional Quality Steps)

### 1. Specify (The "What")
**Goal**: Describe the feature in plain English.
**Command**: `/speckit.specify "I want to add a user login feature"`

**What happens?**
Specify creates a new folder in `specs/` (e.g., `specs/001-user-login/`) and generates a `spec.md` file. 

---

### 🔍 Optional Step: Clarify (The "Details")
**Goal**: Remove confusion before you start planning.
**Command**: `/speckit.clarify`

**What happens?**
Specify reads your `spec.md` and asks you up to 5 targeted questions to fill in missing details (like "How long should a session last?"). It then writes your answers directly into the spec!

---

### 2. Plan (The "How")
**Goal**: Figure out the technical details.
**Command**: `/speckit.plan`

**What happens?**
Specify looks at your `spec.md` and helps you design the solution. It creates `plan.md`, `research.md`, and `data-model.md`.

---

### ✅ Optional Step: Checklist (The "Quality Gate")
**Goal**: Make sure your requirements are well-written.
**Command**: `/speckit.checklist "UX and Security"`

**What happens?**
Specify creates "Unit Tests for English." It doesn't test code; it tests if your *requirements* are clear and complete. It creates files like `ux.md` or `security.md` in a `checklists/` folder.

---

### 3. Task (The "Checklist")
**Goal**: Break the plan into bite-sized pieces.
**Command**: `/speckit.tasks`

**What happens?**
Specify creates a `tasks.md` file. This is your "To-Do List," ordered by priority (P1, P2, P3).

---

### 🧐 Optional Step: Analyze (The "Final Check")
**Goal**: Catch mistakes before you write a single line of code.
**Command**: `/speckit.analyze`

**What happens?**
Specify looks at your `spec.md`, `plan.md`, and `tasks.md` all at once. It checks for:
- **Gaps**: Did you forget to create a task for a requirement?
- **Conflicts**: Does the plan say "Use Python" while the spec says "Use Java"?
- **Ambiguity**: Are there words like "fast" or "secure" that need actual numbers?

---

## 🏃‍♂️ Step 4: Implement (The "Action")
Now it's time to build! You have two ways to do this:

### Option A: The "Manual" Way (You write the code)
1. Open `tasks.md`.
2. Pick the first task (T001).
3. Write the code yourself following the plan.
4. Mark it as done: `- [x] T001 ...`

### Option B: The "Automated" Way (The AI writes the code)
**Command**: `/speckit.implement`

**What happens?**
Specify becomes your **Peer Programmer**. It will:
- Read your `tasks.md`.
- Write the code for you, one task at a time.
- Run tests to make sure the code works.
- Check off the tasks automatically.

> **⚠️ The Lead Engineer Rule**
> Even if the AI writes the code, **YOU** are the boss. You must review the code, run the app, and make sure everything is perfect before you finish. Think of the AI as a very fast Junior Developer—it still needs your guidance!

---

## 🌟 How to Make Your Code Better (Optional Tasks)

To go from "beginner" to "pro," try including these optional steps in your workflow:

### ✅ Test-Driven Development (TDD)
Before you write the actual code, write a **Test**. 
- A test is a tiny script that checks if your code works.
- If you write the test first, you ensure your code actually does what it's supposed to do.

### 🧱 The "Foundation" Phase
In your `tasks.md`, you'll see a **Foundational** section. 
- Spend time getting this right! It's like building the foundation of a house. 
- If your foundation is solid, building the rest of the features will be much easier.

### 🧹 The "Polish" Phase
Don't just stop when the code works. Add a "Polish" task at the end:
- **Refactor**: Clean up messy code.
- **Document**: Write a quick note explaining how the code works.
- **Performance**: Make it run a little faster.

### 🌐 Linking to External Projects (Windows & Mac)
Sometimes, you want your **Specs** in one folder and your **Code** in a completely different folder (or even a different repository). 

You can use `package.json` to "link" them together. The best part? **Forward slashes (`/`) work on both Windows and Mac!**

#### Example: Linking to a separate Code project
```json
{
  "name": "my-specs",
  "dependencies": {
    "my-app-logic": "file:../my-actual-code-folder"
  },
  "workspaces": [
    "../my-actual-code-folder"
  ]
}
```

*   **`file:../...`**: This tells Specify that your code is one folder "up" and then inside `my-actual-code-folder`.
*   **Cross-Platform Tip**: Always use `/` in your JSON and Markdown files. Even on Windows, Node.js and Speckit will understand it perfectly. You don't need to worry about `\` (Windows) vs `/` (Mac).

#### 🤔 What's the difference?
*   **`dependencies` (The "Parts")**: Think of this as ordering a part for a car. You are telling your project: "I need this specific piece of code to work." When you use `file:`, you are telling it to "order" that code from a folder on your computer instead of the internet.
*   **`workspaces` (The "Factory")**: Think of this as having different departments in the same factory. You are telling your computer: "The **Specs** folder and the **Code** folder are partners. They live in the same building and should share everything (like tools and libraries)."

**Recommendation**: For a beginner, using **`workspaces`** is usually the easiest way to keep your Specs and Code connected!

---

## 🔍 How Specify "Sees" Your Code

You might wonder: *"How does Specify know which database I'm using or how I structure my files?"*

During the **Plan** phase, Specify performs **Phase 0: Research**. It doesn't just guess; it acts like a detective:

1.  **Scans Your Files**: It looks for files like `package.json`, `pom.xml`, or `requirements.txt` to see what technologies you already use.
2.  **Uses JSON "Maps"**: It uses files like `package.json` to quickly understand your project's "map"—where your dependencies are, what scripts you run, and how your workspace is organized.
3.  **Follows the Constitution**: It reads your `speckit.constitution` (or `.specify/memory/constitution.md`) to follow your team's rules.
4.  **Learns Your Style**: It explores your existing `src/` folder to understand your naming conventions and where you keep your files.
5.  **Asks Questions**: If it finds something it doesn't understand, it will mark it as `NEEDS CLARIFICATION` in the plan so you can guide it.

This "Research Phase" ensures that the plan it creates isn't just a generic template, but a custom blueprint designed specifically for **your** project.

> **💡 Pro Tip: How Specify Tracks Your Work**
> You don't need to tell Specify which project to implement every time. It uses your **Git Branch name** (e.g., `001-login`) and a hidden file (`.specify/feature.json`) to stay "locked" onto your current feature. The `plan.md` you created tells it exactly which folders (like `src/`, `frontend/`, or `backend/`) it is allowed to modify.

### Example: What Specify looks for in `package.json`
```json
{
  "name": "my-cool-app",
  "version": "1.0.0",
  "scripts": {
    "test": "jest",
    "lint": "eslint ."
  },
  "dependencies": {
    "express": "^4.18.2"
  },
  "devDependencies": {
    "jest": "^29.0.0",
    "typescript": "^5.0.0"
  }
}
```
*   **Dependencies**: Specify sees `express` and knows you are building a web server.
*   **DevDependencies**: It sees `typescript` and `jest`, so it knows to write code in TypeScript and create tests using Jest.
*   **Scripts**: It sees `"test": "jest"` and knows exactly how to run your tests later!

---

## 📖 Glossary for Beginners
- **P1, P2, P3**: Priority levels. P1 is "Must have," P3 is "Nice to have."
- **MVP (Minimum Viable Product)**: The smallest version of your feature that actually works. Usually just User Story 1 (P1).
- **Edge Case**: A "what if" scenario (e.g., "What if the user enters an emoji as their password?").

---

## 🚀 Ready to start?
Type your first command to create a feature:
` /speckit.specify "[Describe your feature here]"`

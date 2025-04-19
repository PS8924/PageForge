# 🧩 PageForge

**PageForge** is a modular, microfrontend-based template builder platform that enables product and marketing teams to compose landing pages, blogs, and storefronts dynamically. Built with Webpack 5 Module Federation, React, and Node.js, it's designed to mimic the development workflows and tooling found in modern startup or SaaS platforms.

---

## 🚀 Why PageForge?

In modern product development, building scalable UIs across multiple teams or feature sets often leads to monolithic frontend codebases. PageForge tackles this by:

- Enabling **independent deployments** of UI modules (e.g., Blog, Landing Page, Store)
- Supporting **plug-and-play** templates that can be previewed live
- Reducing integration friction and improving team velocity

---

## 🏗️ Architecture Overview

           +-----------------------------+
           |        Shell Application    |
           | (Webpack Module Federation) |
           +-----------------------------+
                  /        |         \
                 /         |          \
     +------------+  +------------+  +-------------+
     |  Blog App  |  | Landing UI |  |  Store App  |
     +------------+  +------------+  +-------------+

    ↳ Shared state via Redux, TypeScript Interfaces, Remote Modules


---

## 🧰 Tech Stack

- **Frontend:** React, TypeScript, TailwindCSS
- **Microfrontend Loader:** Webpack 5 Module Federation
- **State Management:** Redux Toolkit
- **Backend Utilities:** Node.js, TypeScript
- **Tooling:** ESLint, Prettier, Jest, GitHub Actions

---

## 📦 Features

- 🧩 Dynamic module federation with real-time preview
- 🎨 Theme switching + basic CMS-like configuration
- ⚙️ Backend scripts to automate remote module registration
- 📂 Shared Redux state across federated apps
- ✅ Jest-based unit testing for critical logic
- 🔄 GitHub Actions for automated CI/CD pipelines

---

## 🚀 Getting Started

```bash
# Clone this repository
git clone https://github.com/your-username/pageforge.git
cd pageforge

# Install dependencies
npm install

# Run shell app
npm run start:shell

# Run any microfrontend app (example: blog)
cd apps/blog
npm install
npm start


📁 Project Structure

pageforge/
├── shell/                # Host shell app
├── apps/
│   ├── blog/             # Blog microfrontend
│   ├── store/            # Store microfrontend
│   └── landing/          # Landing page builder
├── shared/               # Shared components + Redux slices
├── scripts/              # Node.js backend utilities
├── docs/                 # Architecture, State Management, Use Cases
└── .github/workflows/    # GitHub Actions for CI/CD
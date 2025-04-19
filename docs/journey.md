
---

#### 3. **`/docs/journey.md`**

```markdown
# PageForge Development Journey

This section captures the day-by-day development process of building PageForge. Each entry summarizes the tasks accomplished and challenges faced, helping to understand the evolution of the project.

## Day 1: Initial Project Setup
- Set up the basic project structure with Webpack 5, React, and TypeScript.
- Configured Webpack Module Federation for the Shell App to dynamically load remote microfrontends.
- Initialized the `apps/` folder to hold different microfrontend apps (Blog, Store, Landing).

## Day 2: Microfrontend App Integration
- Started working on the Blog microfrontend and integrated it with the Shell App.
- Added basic Redux setup to handle shared state across the Shell and Blog.
- Resolved challenges with routing across federated apps.

## Day 3: State Management and Redux Integration
- Implemented Redux for global state management across all microfrontends.
- Set up a shared `theme` slice to manage UI preferences like dark/light mode across the platform.
- Optimized Redux integration for seamless state updates.

## Day 4: CI/CD and Automation
- Set up GitHub Actions for automated testing and deployment.
- Added backend utility scripts to automate microfrontend module registration, reducing manual setup time.
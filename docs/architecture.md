# PageForge Architecture Overview

PageForge is designed around the concept of **microfrontends**, where each app (e.g., Blog, Store, Landing Page) is independently developed, deployed, and integrated. These microfrontends are hosted by a **Shell Application** that is responsible for loading, displaying, and managing the interaction between these apps.

## Architecture Breakdown

### 1. **Shell Application**
The Shell App acts as the core of the platform and is responsible for:
- Loading remote microfrontends via **Webpack Module Federation**.
- Providing a **global layout**, navigation, and theme.
- Managing **Redux state** across federated apps.
  
### 2. **Remote Microfrontends**
Each of the following microfrontends can be independently developed and deployed:
- **Blog App**: Handles the blog template and content management.
- **Store App**: Manages the e-commerce storefront experience.
- **Landing App**: Provides customizable landing page templates.

These apps interact via **shared Redux slices**, ensuring that global state management is consistent across the entire platform.

### 3. **Shared Components & Utilities**
Shared UI components (like buttons, headers) and state management logic are stored in the `shared/` directory, and can be used across all microfrontends to avoid duplication.

## How It Works
1. The Shell App is loaded first.
2. Remote modules (like Blog, Store) are dynamically loaded when needed using **Webpack Module Federation**.
3. Shared components and Redux store are automatically synced across the apps.

## Future Scalability
- Adding new microfrontends (e.g., "Contact", "About", etc.) is as simple as creating new modules and integrating them into the Shell.
- Theme and layout customization can be done through shared settings across all microfrontends.
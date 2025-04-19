# PageForge State Management

In this project, we use **Redux Toolkit** to manage global state across the Shell App and remote microfrontends. The goal is to maintain **consistent state** across different apps, such as theme preferences, user authentication, or any shared data like page configuration.

## Why Redux?

While **React Context** could manage state for smaller apps, we chose **Redux Toolkit** for its simplicity, scalability, and efficient state management capabilities in a microfrontend environment.

### Key Features
- **Global State**: Centralized state for theme, user info, configuration, etc.
- **State Slices**: Each slice handles different parts of the app (e.g., `userSlice`, `themeSlice`).
- **Shared Across Microfrontends**: Redux store is shared across all microfrontends by leveraging Webpack Module Federation.

### Redux Flow
1. The Shell App initializes the Redux store.
2. Microfrontends (Blog, Store, etc.) connect to the Redux store.
3. Shared state like user preferences or theme settings are stored centrally, allowing them to be accessed and updated by any microfrontend.

### Benefits
- **Consistency**: Ensures that all microfrontends have access to the same data.
- **Performance**: Redux Toolkit simplifies state updates, making it easier to handle complex state flows.
- **Seamless Integration**: Using Redux across all modules ensures smooth data flow between different parts of the platform.

### Example Redux Slice

```ts
import { createSlice, PayloadAction } from '@reduxjs/toolkit';

interface ThemeState {
  theme: string;
}

const initialState: ThemeState = {
  theme: 'light',
};

const themeSlice = createSlice({
  name: 'theme',
  initialState,
  reducers: {
    setTheme: (state, action: PayloadAction<string>) => {
      state.theme = action.payload;
    },
  },
});

export const { setTheme } = themeSlice.actions;
export default themeSlice.reducer;

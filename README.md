# Nuxt.js: LocalStorage Session Persistence

## Overview

This repository shows in a very simple and practical example how I implemented session persistent in my Nuxt.js app [OneExercise](https://oneexercise.mstflotfy.com/) in isolation of the complexity of the app.


The repository provides a clear guide on implementing session persistence using localStorage in a Nuxt.js application. It demonstrates how to persist data across page reloads or app closures. Here are the key features and steps to get started:

## Key Features

- **Isolated example:** Demonstrates the use of localStorage within the application, separate from complex app code.
- **Clear Code Examples:** Shows how to set, get, and remove data from localStorage in a Nuxt application.

## Getting Started

1. **Clone the Repository:**

   ```bash
   git clone https://<your_github_username>/nuxt-isolated-localStorage.git
   ```

2. **Install Dependencies:**

   ```bash
   npm install
   ```

3. **Run the Development Server:**

   ```bash
   npm run dev
   ```

4. **Explore Code Examples:**

   Examine the `pages` directory to understand how localStorage is used for session management.

## Branch Structure

- **main:** Contains the fundamental implementation of localStorage session management.
- **improved:** This branch builds upon the `main` branch.

## Important Considerations

- **Suitability:**  Ideal for persisting non-critical data like user preferences or selections across sessions.

For more details and examples, you can refer to the provided links:

- [Client-side storage, mdn web docs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage#storing_simple_data_%E2%80%94_web_storage)
- [Using the Web Storage API, mdn web docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API#basic_concepts)
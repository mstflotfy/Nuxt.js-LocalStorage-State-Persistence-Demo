# Nuxt.js LocalStorage State Persistence Demo

## Overview

This repository provides a simple and practical demonstration of how to implement 
client-side state persistence using localStorage in a Nuxt.js application. 
The example is extracted from the [OneExercise](https://oneexercise.mstflotfy.com/) app, 
isolating the localStorage implementation from the app's complexity.

The demo showcases how to persist data across page reloads or app closures using localStorage in a Nuxt.js application. 
Here are the key features and steps to get started:

## Key Features

- **Isolated Example:** Demonstrates the use of localStorage for client-side state persistence, 
separate from complex app code.
- **Clear Code Examples:** Shows how to set, get, and remove data from localStorage in a Nuxt.js application.

## Getting Started

1. **Clone the Repository:**

   ```bash
   git clone https://<your_github_username>/Nuxt.js-LocalStorage-State-Persistence-Demo
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

   Examine the `pages` directory to understand how localStorage is used for client-side state persistence.

## Branch Structure

- **main:** Contains the fundamental implementation of localStorage state persistence.
- **improved:** This branch builds upon the `main` branch with additional enhancements or features.

## Important Considerations

- **Suitability:** Using localStorage is ideal for persisting non-critical data like user preferences or selections across sessions on the client-side.

For more details and examples, you can refer to the provided links:

- [Client-side storage, mdn web docs](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Client-side_web_APIs/Client-side_storage#storing_simple_data_%E2%80%94_web_storage)
- [Using the Web Storage API, mdn web docs](https://developer.mozilla.org/en-US/docs/Web/API/Web_Storage_API/Using_the_Web_Storage_API#basic_concepts)



# 📌 Random-Facts

A simple Vue.js application that fetches coding exercises from an external API and displays them to the user.
Each time the user clicks the “New Exercise” button, they receive a **random exercise** from the list.

---

## 🚀 Overview

This project is built as part of a series of coding exercises completed on a learning platform.
The application reads the exercise data from an API, displays them in the UI, and allows the user to request a random new exercise at any time.

This project was also uploaded to my GitHub as part of documenting my learning progress.

---

## 🛠️ Features

* Fetches exercise data from an API
* Displays exercises in a clean interface
* Shows **one random exercise** per request
* Simple, lightweight, and easy to extend
* Built with Vue 3 + Vite

---

## 🧰 Tech Stack

* **Vue.js 3**
* **Vite**
* **Axios** for API requests
* **TailwindCSS (optional)**

---

## 📦 Installation

### Clone repository

```bash
git clone https://github.com/your-username/vue-exercise-viewer.git
cd vue-exercise-viewer
```

### Install dependencies

```bash
npm install
```

### Run development server

```bash
npm run dev
```

### Build for production

```bash
npm run build
```

---

## 🔌 API Example (Used in Project)

`src/services/api.js`

```js
import axios from "axios";

const api = axios.create({
  baseURL: "https://example.com/api/exercises",
});

export default api;
```

---

## 🎯 How It Works

### 1. Fetch exercises from API:

```js
const exercises = await api.get("/");
```

### 2. Save them in component state

### 3. Generate a random exercise:

```js
function getRandomExercise() {
  const index = Math.floor(Math.random() * exercises.value.length);
  currentExercise.value = exercises.value[index];
}
```

### 4. Display result in UI

User clicks **"New Exercise"** → UI updates →

---

## 📁 Project Structure

```
src/
├─ components/
│  └─ ExerciseCard.vue
├─ views/
│  └─ HomeView.vue
├─ services/
│  └─ api.js
├─ App.vue
└─ main.js
```

---

## 🙌 Why I Built This

I completed a number of exercises on a coding platform and wanted to create a small project to:

* Practice Vue.js
* Learn API consumption
* Improve component structure
* Upload it as a learning milestone on GitHub

---

## 📝 License

MIT License

---

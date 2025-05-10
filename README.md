# Rule-Based
# Rule-Filter_based# Rule-Based
# Installation & Dependencies

## Backend (Flask)

### Install Dependencies
```sh
pip install flask flask-cors
```

### Run the Backend
```sh
python app.py
```

## Frontend (React + Vite)

### Create a Vite Project
```sh
npm create vite@latest frontend --template react
cd frontend
```

### Install Dependencies
```sh
npm install
```

### Set Up Tailwind CSS
```sh
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

Modify `tailwind.config.js`:
```js
export default {
  content: ["./index.html", "./src/**/*.{js,ts,jsx,tsx}"],
  theme: {
    extend: {},
  },
  plugins: [],
};
```

Modify `src/index.css`:
```css
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Run the Frontend
```sh
npm run dev

```
# 🧠 RAG Customer Intelligence Assistant

A Retrieval-Augmented Generation (RAG) system that allows natural language querying over a structured customer dataset using FAISS, HuggingFace embeddings, and a locally running LLaMA 3.2 model via Ollama.

---

## 📦 Features

- 🔍 Ask **any question** about 500 customers — based on **email**, **address**, **avatar color**, **time on app**, **time on website**, **membership length**, and **yearly spend**.
- 🧠 RAG-powered: Uses vector embeddings of structured customer profiles for high-relevance answers.
- 📄 Returns **formatted profiles with auto-generated summaries**.
- 🧾 Includes **source document excerpts** for transparency.
- ⚙️ Powered by **LangChain**, **FAISS**, **MiniLM**, and **Ollama (LLaMA 3.2)**.

---

## 📁 Project Structure
rag-customer-assistant/
│
├── data/
│ └── customers.csv # Original dataset (500 entries)
│
├── embeddings/
│ └── rag_customer_faiss/ # Vector store with FAISS index + metadata
│
├── scripts/
│ ├── generate_profiles.py # CSV → structured profiles with summaries
│ └── embed_profiles.py # Embeds profiles into FAISS using MiniLM
│
├── app/
│ ├── main.py # Chat interface to query the RAG model
│ └── prompt_template.py # LangChain prompt customization
│
├── requirements.txt # Python dependencies
└── README.md # You're reading it


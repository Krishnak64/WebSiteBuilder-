# WebSiteBuilder 🏗️

An AI-powered website builder built with the **MERN stack**, integrating the **OpenRouter API** for AI-assisted generation, a **Monaco code editor** for live code editing, **Firebase** for auth/storage, and **Stripe** for payments.

🔗 **Live Demo:** [websitebuilder-3p61.onrender.com](https://websitebuilder-3p61.onrender.com)

---

## 📖 Table of Contents

- [Features](#-features)
- [Tech Stack](#-tech-stack)
- [Project Structure](#-project-structure)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Environment Variables](#-environment-variables)
- [Running the Project](#-running-the-project)
- [Build for Production](#-build-for-production)
- [Deployment](#-deployment)
- [Contributing](#-contributing)
- [License](#-license)

---

## ✨ Features

- 🤖 **AI-powered website generation** using the OpenRouter API
- 📝 **In-browser code editor** with syntax highlighting (Monaco Editor)
- 🔐 **Authentication** via Firebase and JWT-based sessions
- 💳 **Payments/subscriptions** powered by Stripe
- 🗂️ **State management** with Redux Toolkit
- 🎨 **Modern styling** with Tailwind CSS
- 🚏 **Client-side routing** with React Router
- 🍪 **Secure cookie handling** with cookie-parser
- 🌐 **REST API backend** with Express 5 and MongoDB (Mongoose)

---

## 🛠️ Tech Stack

**Frontend (`/client`)**
- React 19 + Vite 7
- Redux Toolkit / React Redux
- React Router DOM
- Tailwind CSS 4
- Monaco Editor (`@monaco-editor/react`)
- Firebase SDK
- Axios
- Motion (animations)
- Lucide React (icons)

**Backend (`/server`)**
- Node.js + Express 5
- MongoDB + Mongoose
- JSON Web Token (JWT) authentication
- Cookie-parser
- CORS
- Stripe (payments)
- Dotenv
- Nodemon (dev)

**AI**
- OpenRouter API for AI-assisted website/content generation

---

## 📁 Project Structure

WebSiteBuilder/
├── client/                          # React frontend
│   ├── src/
│   │   ├── assets/
│   │   ├── components/
│   │   │   └── LoginModal.jsx       # Login/auth modal
│   │   ├── hooks/
│   │   │   └── useGetCurrentUser.jsx
│   │   ├── pages/
│   │   │   ├── Dashboard.jsx        # User dashboard
│   │   │   ├── Editor.jsx           # Website editor page
│   │   │   ├── Generate.jsx         # AI generation page
│   │   │   ├── Home.jsx             # Landing page
│   │   │   ├── LiveSite.jsx         # Published/live site view
│   │   │   └── Pricing.jsx          # Pricing/plans page
│   │   ├── redux/
│   │   │   ├── store.js             # Redux store config
│   │   │   └── userSlice.js         # User auth/state slice
│   │   ├── App.jsx
│   │   ├── firebase.js              # Firebase config/init
│   │   ├── index.css
│   │   └── main.jsx
│   ├── index.html
│   ├── vite.config.js
│   ├── eslint.config.js
│   ├── .env
│   ├── .gitignore
│   └── package.json
│
├── server/                          # Express backend
│   ├── config/                      # DB & service configuration
│   ├── controllers/
│   │   ├── billing.controller.js    # Billing/subscription logic
│   │   ├── stripeWebhook.controller.js
│   │   └── user.controllers.js
│   ├── middlewares/
│   │   └── isAuth.js                # JWT auth middleware
│   ├── models/                      # Mongoose schemas
│   ├── routes/
│   │   ├── user.routes.js
│   │   └── website.routes.js
│   ├── utils/
│   │   ├── plan.js                  # Subscription plan helpers
│   │   └── stripe.js                # Stripe client setup
│   ├── index.js                     # Server entry point
│   ├── .env
│   ├── .gitignore
│   └── package.json
│
└── README.md




## ✅ Prerequisites

Before you begin, make sure you have the following installed:

- [Node.js](https://nodejs.org/) (v18 or higher recommended)
- [npm](https://www.npmjs.com/) (comes with Node.js)
- [MongoDB](https://www.mongodb.com/) (local instance or a [MongoDB Atlas](https://www.mongodb.com/atlas) cluster)
- A [Firebase](https://firebase.google.com/) project (for authentication/storage)
- A [Stripe](https://stripe.com/) account (for payments)
- An [OpenRouter](https://openrouter.ai/) API key (for AI generation)

---

## 🚀 Installation

1. **Clone the repository**

   ```bash
   git clone https://github.com/Krishnak64/WebSiteBuilder-.git
   cd WebSiteBuilder-
   ```

2. **Install server dependencies**

   ```bash
   cd server
   npm install
   ```

3. **Install client dependencies**

   ```bash
   cd ../client
   npm install
   ```

---

## 🔑 Environment Variables

Create a `.env` file inside **both** the `server/` and `client/` folders.

### `server/.env`

```env
PORT=5000
MONGO_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret_key
CLIENT_URL=http://localhost:5173

# Stripe
STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_WEBHOOK_SECRET=your_stripe_webhook_secret

# OpenRouter AI
OPENROUTER_API_KEY=your_openrouter_api_key
```

### `client/.env`

```env
VITE_FIREBASE_API_KEY= "your firebase api"
```

> ⚠️ **Never commit your `.env` files.** Make sure both are listed in `.gitignore`.

---

## ▶️ Running the Project

You'll need **two terminals** — one for the backend and one for the frontend.

**Terminal 1 — Start the backend server**

```bash
cd server
npm run dev
```

The server will start on `http://localhost:5000` (or the `PORT` you set).

**Terminal 2 — Start the frontend**

```bash
cd client
npm run dev
```

The client will start on `http://localhost:5173` (Vite's default port).

Open your browser and navigate to `http://localhost:5173` to use the app.

---

## 📦 Build for Production

To create an optimized production build of the client:

```bash
cd client
npm run build
```

The output will be generated in `client/dist`. Preview it locally with:

```bash
npm run preview
```

---

## ☁️ Deployment

This project is deployed on [Render](https://render.com/):

- **Backend:** Deploy the `server/` folder as a Web Service (start command: `node index.js` or `npm run dev` for nodemon).
- **Frontend:** Deploy the `client/` folder as a Static Site (build command: `npm run build`, publish directory: `dist`).

Make sure to set all the environment variables listed above in your Render (or other hosting provider's) dashboard, and update `CLIENT_URL` / `VITE_API_BASE_URL` to point to your deployed URLs.

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repository
2. Create a new branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m "Add some feature"`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request


## 👤 Author

**Krishna**
GitHub: [@Krishnak64](https://github.com/Krishnak64)

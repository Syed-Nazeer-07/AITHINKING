💬 AI Thinking: Multimodal Chat Application

AI Thinking is a fully responsive, single-page web application that provides a real-time, multimodal chat interface powered by the Gemini API. It features secure user authentication via Google and persistent chat history storage using Google Firestore.

✨ Features

Multimodal Chat: Send both text prompts and images in a single message (via the Gemini API).

Real-time Persistence: Chat history is securely stored and synchronized across devices using Google Firestore for logged-in users, or persisted locally for guests.

User Authentication: Seamless login/logout using Firebase Authentication with Google Sign-In.

Responsive Design: Optimized layout for mobile, tablet, and desktop viewports using Tailwind CSS.

Theme Toggling: Supports manual and system-preference-based Light/Dark Mode.

Code & Markdown Rendering: Renders complex markdown (including tables, lists) and highlights code blocks using marked.js and highlight.js.

🛠️ Technologies Used

Frontend: HTML5, Plain JavaScript (ES modules), CSS3 (via Tailwind CSS CDN)

Styling: Tailwind CSS

Backend/Services:

AI Model: Google Gemini API (gemini-2.5-flash-preview-09-2025)

Database: Google Cloud Firestore

Authentication: Firebase Authentication

🚀 Setup and Installation

This application is designed to run as a single HTML file but requires configuration for both the Gemini API and Firebase.

1. Configure the Gemini API Key

You must replace the placeholder API key in index.html.

Get your Gemini API Key from Google AI Studio.

Find the following line in the <script type="module"> block near the bottom of index.html and replace the placeholder value:

// index.html (around line 900)
const API_KEY = "AIzaSyD_ENXxC43nAjHB01QRYZeI9P-UuJK_Kcc"; // <-- REPLACE THIS
const API_URL = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-09-2025:generateContent?key=${API_KEY}`;


2. Configure Firebase (Auth and Firestore)

The app is pre-configured with the structure for Firebase, but if you want to use your own instance for production, you must update the config object.

Set up a new Firebase Project and enable:

Firestore Database (start in production mode with security rules configured for authenticated reads/writes).

Authentication (enable Google as a sign-in provider).

Find the firebaseConfig object in the same <script type="module"> block and update the credentials with your project's configuration.

// index.html (around line 865)
const firebaseConfig = {
    apiKey: "YOUR_FIREBASE_API_KEY", // <--- REPLACE THIS
    authDomain: "your-project-id.firebaseapp.com",
    projectId: "your-project-id",
    // ... rest of the config
};


3. Run the Application

Since this is a single HTML file, you can run it by simply opening index.html in your web browser.

💡 Usage

Guest Mode: By default, if you are not logged in, the app operates in Guest Mode, saving chat history to your browser's local storage.

Login: Click "Login with Google" to enable real-time persistence and access your chat history across devices via Firestore.

Chatting: Type your prompt into the input box. Use the Paperclip icon (📎) to attach an image to your message.

History: Use the sidebar to switch between or start new chat conversations.

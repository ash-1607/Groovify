# Groovify (Full-Stack Spotify AI Companion)

Groovify is a secure, full-stack mobile application that enhances the Spotify user experience with generative AI, personalized analytics, and advanced data-driven features.

The architecture utilizes a **Backend-for-Frontend (BFF)** pattern deployed on Vercel to securely handle all OAuth authentication and third-party AI integrations.

## 📱 User Guide & Installation

If you are a user, follow these steps to get the app running:

1.  **Download the APK:** [Link to your `Groovify.apk` file on GitHub Releases or a hosting platform].
2.  **Install:** Allow installation from unknown sources on your Android device if necessary.
3.  **Log In:** Open the app and securely log in using your Spotify account.

### ✨ Key Features

  * **🎧 Personalized Music Insights:** Groovify's advanced AI analyzes your listening history to generate witty, shareable summaries of your music taste and current mood.
  * **💎 Rediscover Old Favorites:** The "Forgotten Gems" feature automatically curates a unique playlist of tracks you used to love but haven't played in a while, ensuring you never lose touch with your best tracks.
  * **🎨 Instant Playlist Makeover:** Use the AI Playlist Artist to instantly create a stylish description and stunning, custom cover art for any playlist you own.
  <!-- * **🔒 Seamless, Secure Experience:** Enjoy continuous access without repeated logins. Groovify handles authentication securely, providing a smooth, auto-login experience every time you open the app. -->

-----

## ⚙️ Developer Setup & Architecture

This section is for developers interested in contributing, reviewing the code, or running the project locally.
<br>
Note: This section is under updation so if you face any issues, wait for few days, or else contact me at ashmeetsidhu04@gmail.com.

### 🛠 Tech Stack

| Component | Technology | Role |
| :--- | :--- | :--- |
| **Backend** | FastAPI (Python) | Secure Backend-for-Frontend (BFF), API, and OAuth handler. |
| **Mobile** | React Native / TypeScript | Cross-platform client application (iOS/Android). |
| **AI/ML** | OpenRouter (Grok-4) & Clipdrop | Generative AI for analysis and image creation. |
| **Deployment** | **Vercel** | Production hosting for the FastAPI BFF server. |

### 📝 Prerequisites

  * Python 3.10+
  * Node.js & npm
  * `ngrok` CLI tool
  * Spotify Developer App credentials
  * API keys for OpenRouter and Clipdrop

### 🔑 Configuration (`.env`)

In your `/backend` directory, create a `.env` file containing your secrets. The `SPOTIFY_REDIRECT_URI` must match your Spotify Dashboard setting and will use the `ngrok` URL for local development.

```
SPOTIFY_CLIENT_ID=...
SPOTIFY_CLIENT_SECRET=...
SPOTIFY_REDIRECT_URI=https://<your-ngrok-url>.app/callback
APP_SECRET_KEY=... (random 32-char key)
OPENROUTER_API_KEY=...
CLIPDROP_API_KEY=...
```

### 🏃 Local Run Instructions

You need **three terminals** open to run the full stack locally:

1.  **Backend (Terminal 1):**
    ```bash
    cd backend
    uvicorn app_step3:app --host 0.0.0.0 --port 8000 --reload
    ```
2.  **ngrok Tunnel (Terminal 2):**
      * This is required because Spotify OAuth demands an HTTPS redirect URI, even for local development.
    ```bash
    ngrok http 8000
    ```
3.  **Mobile App (Terminal 3):**
    ```bash
    cd mobile-app
    npx react-native run-ios # or run-android
    ```
    ***Remember to update the `API_BASE_URL` in `mobile-app/src/api.ts` to the ngrok URL\!***

<!-- ## 🤝 Contributing

(Add your contribution guidelines here, e.g., how to file issues, or if you are not accepting pull requests.)

-----

**Do you want to add a contribution guide or a license section, or are you ready to use this README?** -->


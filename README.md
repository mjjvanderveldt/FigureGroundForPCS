# Figure Ground Perception Trainer

A browser-based visual training tool designed to improve figure-ground discrimination skills, often used to aid recovery from post-concussion syndrome.

It generates a chaotic, procedurally generated background using the HTML5 Canvas API to "camouflage" scattered text characters. The user must visually isolate the static letters from the moving noise.

## 🚀 Features

-   **Procedural Chaos:** Three distinct noise modes (Geometric Shapes, Digital Rain, Chaotic Lines).
    
-   **Collision-Free Scattering:** Algorithms ensure letters are randomly placed but **never overlap** with each other.
    
-   **Smart Layout:** "Safe zones" prevent letters from being hidden behind UI controls or the timer.
    
-   **Stopwatch & Leaderboard:** Integrated timer with start/stop functionality.
    
-   **Cloud Persistence:** Automatically saves completion times to Firebase Firestore, allowing history to persist across sessions (per user).
    
-   **Responsive Design:** Adapts to window resizing dynamically.
    

## 🎮 How to Use

1.  **Start the Timer:** Click `▶ Start` to begin the session.
    
2.  **The Task:** Visually locate all scattered letters amidst the moving background noise.
    
3.  **Stop & Log:** Once the task is complete (e.g., you have read all letters aloud), click `⏹ Stop`.
    
    -   _Note:_ The time is automatically saved to your history if the duration is longer than 0.1 seconds.
        
    -   The **History Panel** will open automatically to show your new record.
        
4.  **Scramble:** Press **Spacebar** or click `Randomize Positions` to reshuffle the letters for a new round.
    

### Controls

-   **Spacebar:** Randomize letter positions and rotation.
    
-   **⚙️ Settings:** Open the control panel to adjust:
    
    -   **Chaos Speed:** How fast the background distractors move.
        
    -   **Pattern Density:** How many distractors appear on screen.
        
    -   **Change Pattern:** Cycle through the 3 visual noise modes.
        
-   **🏆 History:** Toggle the personal leaderboard view.
    

## 🛠️ Technical Setup

### Running the Application

This is a **Single-File Application** containing HTML, CSS, and JavaScript.

1.  **Browser:** Open `index.html` in any modern web browser (Chrome, Edge, Firefox, Safari).
    
2.  **Internet:** An internet connection is required to load the Firebase SDK and save/load history data.
    

### Firebase Configuration

The application expects Firebase configuration variables to be present in the global scope. If running locally or outside of the generated environment, you must inject these values before the main script runs, or edit the `<script>` tag in `index.html`:

```
// Example manual configuration in index.html if not using environment injection
const __firebase_config = JSON.stringify({
  apiKey: "YOUR_API_KEY",
  authDomain: "YOUR_PROJECT.firebaseapp.com",
  projectId: "YOUR_PROJECT_ID",
  // ... other config
});
const __app_id = "figure-ground-v1";

```

### Architecture Details

-   **Frontend:** Vanilla JavaScript (ES6 Modules).
    
-   **Rendering:** HTML5 Canvas (2D Context) for noise; DOM elements for letters (for crisp typography).
    
-   **Data:** Firebase Firestore.
    
    -   **Collection Path:** `artifacts/{appId}/users/{uid}/leaderboard`
        
    -   **Queries:** Data is fetched via `onSnapshot` and sorted client-side (in-memory) to minimize database index requirements.
        
-   **Auth:** Firebase Anonymous Auth (or Custom Token if provided).
    

## 🎨 Customization

To modify the difficulty or aesthetics, edit the configuration variables in the `<script>` section of `index.html`:

-   **Change Characters:** Edit the `alphabetLower` string (e.g., change to numbers `"0123456789"`).
    
-   **Colors:** Modify the `getRandomColor()` function to change the distractor palette.
    
-   **Sizing:** Adjust `minSize` and `maxSize` within the `scatterLetters()` function to change target visibility.
    

## ⚠️ Disclaimer

**I am not a doctor or medical professional.** This software is provided for educational and entertainment purposes only. It is not intended to diagnose, treat, cure, or prevent any disease or medical condition, including post-concussion syndrome. Always seek the advice of your physician or other qualified health provider with any questions you may have regarding a medical condition or visual therapy regimen.

## 📄 License

This project is open source and free to use for personal or educational purposes.

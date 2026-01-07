# Figure Ground Perception Trainer

A browser-based visual training tool designed to improve figure-ground discrimination skills. It generates a chaotic, procedurally generated background using the HTML5 Canvas API to camouflage scattered text characters.

## 🚀 How to Use

1. **Download:** Save the code as an `.html` file (e.g., `index.html`).
2. **Run:** Double-click the file to open it in any modern web browser (Chrome, Firefox, Safari, Edge).
3. **No Installation:** This is a single-file application. No internet connection, server, or dependencies are required.

## 🎮 Controls

* **Spacebar:** Randomize the positions and sizes of the letters.
* **Settings Button (⚙️):** Toggle the control panel.
* **Chaos Speed:** Adjust how fast the background pattern updates.
* **Pattern Density:** Adjust how cluttered the background is.
* **Change Pattern:** Cycle between three modes:
  1. Geometric Shapes
  2. Digital "Rain" Noise
  3. Chaotic Lines

## 🛠️ Customization

If you want to modify the code:
* **Change Letters:** Edit the `alphabetLower` string in the script to use numbers or symbols.
* **Adjust Colors:** Modify the `getRandomColor()` function to change the background palette.
* **Resize:** Modify the `minSize` and `maxSize` variables in the `scatterLetters()` function.

## 📄 License

This project is open source and free to use for personal or educational purposes.

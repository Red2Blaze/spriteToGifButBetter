# ✨ Sprite-to-GIF Converter

A purely local, browser-based tool to convert transparent PNG sprite sheets into high-quality animated GIFs. 

### Before & After
*(Replace the links below with the paths to your actual images once uploaded to your repo)*

| Original Sprite Sheet | Generated GIF |
| :---: | :---: |
| <img src="img/Sprite%20sheet%20eating%20noodles%20v2.png" width="300" alt="My Sprite Sheet"> | <img src="/img/Sprite%20sheet%20eating%20noodles-animated%20v3.gif" width="150" alt="Finished GIF"> |

## 💡 Why I Built This

I was working on a specific GIF project and tried a few different online converters to animate my sprite sheets. While there are a lot of great tools out there, some didn't support transparent backgrounds, and others required the sprites to be aligned perfectly in a strict grid to work. 

I decided to just make my own simple tool to handle exactly what I needed so I could get my project done easily!

## 🚀 Features

* **✨ Auto-Detect Frames:** Uses a custom flood-fill algorithm to automatically scan the image, find individual sprites, and perfectly center them in bounding boxes.
* **🖱️ Drag-and-Drop Manual Edits:** Left-click to add a new frame, click and drag to adjust its position, and right-click to delete it.
* **🎨 Flawless Transparency:** Processes pixels individually to apply a hard alpha-threshold *before* encoding. This completely prevents the pink/white fringing usually seen on transparent GIFs.
* **📂 Fully Local:** No server uploads required. Everything runs locally in your browser using JavaScript and Web Workers.

## 🛠️ How to Run It Locally

Because this tool uses Web Workers to encode the GIF in the background without freezing the webpage, modern browsers require it to be run through a local web server (opening the HTML file directly via `file:///` will block the worker for security reasons).

**Prerequisites:** Ensure you have the `gif.js` and `gif.worker.js` files in the same directory as `index.html`.

**Option 1: Visual Studio Code (Easiest)**
1. Open the project folder in VS Code.
2. Install the **Live Server** extension.
3. Right-click `index.html` and select **Open with Live Server**.

**Option 2: Python (Mac/Linux/Windows)**
1. Open your terminal or command prompt.
2. Navigate to the project folder.
3. Run: `python -m http.server` (or `python3 -m http.server`)
4. Open your browser and go to `http://localhost:8000`.

**Option 3: Node.js**
1. Open your terminal in the project folder.
2. Run: `npx http-server`
3. Open your browser to the provided localhost address.

## 💻 Tech Stack
* **HTML5 / CSS3 / JavaScript (Vanilla)**
* [gif.js](https://jnordberg.github.io/gif.js/) - For fast, hardware-accelerated GIF encoding in the browser.

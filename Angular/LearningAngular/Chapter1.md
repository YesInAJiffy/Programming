
# Setup in a Chromebook

---

### Option 1: The "Pro" Way (Linux Development Environment)

Most modern Chromebooks (made after 2019) have a feature called **Crostini**. This allows you to run a full Linux terminal, which is the native habitat for Angular.

**How to set it up:**

1. **Enable Linux:** Go to `Settings` > `Advanced` > `Developers` > `Linux development environment` and turn it on.
2. **Install Node.js:** Open your new Terminal and run:
```bash
sudo apt update
sudo apt install -y nodejs npm

```


3. **Install the Angular CLI:** This is the tool that builds your apps:
```bash
npm install -g @angular/cli

```


4. **Install VS Code:** You can download the `.deb` version of Visual Studio Code from their website and install it directly into your Linux environment.

---

### Option 2: The "Cloud" Way (No Setup Required)

If your Chromebook is an older model or has low storage/RAM, you can use a browser-based IDE. This is actually how many professional developers work in 2026 to save battery life.

* **StackBlitz:** This is the "Gold Standard" for Angular. It has a specific **Angular Generator** that sets up a full project in your browser in 2 seconds.
* **URL:** [stackblitz.com](https://stackblitz.com)


* **GitHub Codespaces:** If you host your code on GitHub, you can press the `.` key on your keyboard while looking at your repository, and it will open a full version of VS Code in your browser.

---

### Why Chromebooks are good for learning Angular

* **TypeScript Integration:** TypeScript is a "superset" of JavaScript. It doesn't require a heavy machine to compile; your browser or a simple Linux terminal handles it easily.
* **The Development Server:** When you run `ng serve`, Angular creates a local web server. On a Chromebook, you just navigate to `localhost:4200` in Chrome, and your app appears instantly.
* **Battery Life:** Because ChromeOS is lightweight, you can often code for 8–10 hours on a single charge compared to 3–4 hours on a heavy Windows laptop.

---

### A Quick "Learning Map" for You

Since you are starting with Angular and TypeScript, follow this order:

1. **TypeScript First:** Learn about **Interfaces** and **Types**. (e.g., `let patientId: string = "123";`)
2. **Components:** The building blocks of Angular.
3. **Services & Dependency Injection:** This connects perfectly to our "Domain" conversation earlier! In Angular, a **Service** is often how you share data between different parts of your app.
4. **Observables (RxJS):** How Angular handles "Events" (like the messages in our Saga/Outbox discussion).

---

### One Limitation to Watch Out For

**RAM (Memory):** Angular is a "heavy" framework. If your Chromebook has only **4GB of RAM**, it might struggle if you have 20 Chrome tabs open while trying to run the Angular compiler. Try to have at least **8GB** for a smooth experience.

**Would you like me to give you the first "Hello World" code for an Angular Component so you can see how TypeScript is used inside the framework?**

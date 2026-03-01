# 🐍 Python Environments on Ubuntu Guide 

This guide helps you create a **Virtual Environment**. Think of it as a "private container" for your project so its files don't get mixed up with your computer's main settings.

---

## 🛠️ Step 1: Prep your Computer

Run this **once** to ensure Ubuntu has the specific tool needed to build these "containers":

```bash
sudo apt update && sudo apt install python3-venv -y

```

---

## 📁 Step 2: Create your Project Folder

You need a place for your code to live. You can change `my-project` to any name you like.

**Option A (Terminal):**

```bash
mkdir my-project && cd my-project

```

**Option B (File Manager):**

1. Create a new folder (e.g., `my-project`).
2. **Right-click** inside that folder and select **"Open in Terminal"**.

---

## 🚀 Step 3: Setup your "Sandbox"

### 1. Create the environment

This creates a folder named `.venv` inside your project.
*(Make sure your terminal prompt shows your project name, e.g., `~/my-project$ `)*

```bash
python3 -m venv .venv

```

> [!NOTE]
> **Can't see the folder?** Because the name starts with a dot (`.`), Ubuntu hides it. Press **`Ctrl + H`** in your file manager to toggle hidden files!

### 2. Turn it on (Activate)

This tells your computer to use the sandbox instead of the global system.

```bash
source .venv/bin/activate

```

> [!TIP]
> **How do I know it worked?** You will see **`(.venv)`** appear at the very start of your terminal text line.

---

## 💻 Step 4: Link to VS Code

VS Code needs to know to look inside your "sandbox" for your libraries.

1. Open your project folder in VS Code.
2. **Look for a popup:** In the bottom right, VS Code may ask: *"We noticed a new environment... would you like to select it?"* Click **Yes**.
3. **Manual fix (if no popup):**
* Press **`Ctrl + Shift + P`**.
* Type **"Python: Select Interpreter"**.
* Pick the version that shows the path **`./.venv/bin/python`**.



---

## 📦 Installing Libraries

Once you see **`(.venv)`** in your terminal, you can safely install tools:

* **Install a tool (e.g., pandas):** `pip install pandas`
* **Save your "recipe" list:** `pip freeze > requirements.txt`
* **Install from a "recipe" list:** `pip install -r requirements.txt`

> [!IMPORTANT]
> Always ensure **`(.venv)`** is visible before typing `pip install`. If it's not there, you are installing to your main computer system!

---

## 🛑 When you're finished

To leave the environment and return to your main system:

```bash
deactivate

```

---

## 📖 Cheat Sheet

| Task | Command | Visual Cue | When? |
| --- | --- | --- | --- |
| **Setup Ubuntu** | `sudo apt install...` | Done once | Only once ever |
| **Create Sandbox** | `python3 -m venv .venv` | `.venv` folder appears | Once per project |
| **Enter Sandbox** | `source .venv/bin/activate` | **`(.venv)`** in prompt | Every time you code |
| **Exit Sandbox** | `deactivate` | **`(.venv)`** disappears | When you're done |

---
## 📂 Moving or Copying Projects
You can have as many **Project folders** as you like on your desktop, each with its own `.venv`. However, virtual environments cannot be moved.

If you drag and drop your project folder to a new folder location, the `.venv` inside it will break because it remembers its old `"address-path"`

**To move a project safely:**

Delete the existing `.venv` in your current folder.

Move your projects to the new folder location you have just made.

Open a terminal in the **new folder location** and create a fresh environment and activate it 👇:

```Bash
# 1. Create the new environment
python3 -m venv .venv

# 2. Activate it immediately
source .venv/bin/activate
```
>[!IMPORTANT]
>Once activated, you will see `(.venv)` in your terminal. You can then re-install your libraries (e.g., `pip install pandas`), etc.
___
## ⚠️ Disclaimer 

This project is provided "as-is" without any warranty of any kind. I am not responsible for any issues, data loss, or "explosions" (code-related or otherwise) that may occur from using this software. **Use it at your own risk.**
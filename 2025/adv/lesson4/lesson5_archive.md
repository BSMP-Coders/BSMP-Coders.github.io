# 🎮 Week 2, Lesson 5: Build Your First Pygame Project with GitHub Copilot <!-- {docsify-ignore-all} -->

> [!LESSON_REPO]
>
> Refer to this <i class="fab fa-github"></i> [Lesson 5 Repository](https://github.com/BSMP-Coders/advanced-game-dev/tree/main/lesson-2) for lesson details and activities for this lesson.

-----


## Welcome to your first video game!

You're about to dive into Pygame the Python toolkit that turns your ideas into playable games with graphics, sounds, and all the fun stuff that makes games amazing. This lesson will guide you step-by-step to create something you can actually play and share.


## 🎯 What You'll Do

By the end of this lesson, you'll be able to:
- **Create your first game** - Build a working game using Python and GitHub Copilot
- **Master GitHub collaboration** - Share your project and give feedback like a pro developer


## 🛠️ Setup Checklist

So far, you've been working in a cloud-based development tool in the browser called GitHub Codespaces. For this lesson Pygame works best when run locally on a computer, this requires you to use Visual Studio Code and cloning your repository.

**Step 1: Get Python**
- Go to the Windows Store and install **Python 3.13**
- OR open the command line and type `python` (it'll take you to the installation page automatically!)

**Step 2: Download Your Code Editor**
- Download and install **Visual Studio Code** from the Windows Store
- This will be your game development headquarters!

**Step 3: Connect to Your Project**
- Open Visual Studio Code
- Go to **Source Control** > **Clone** (under the three dots)
- Follow the instructions to fork and clone the repository
- Now you have your own copy to work with!

**Step 4: Add Your AI Coding Assistant**
- In VS Code, click the Extensions icon in the Activity Bar
- Search for **"GitHub Copilot"** and install it
- Your AI pair programmer is now ready to help!

**Step 5: Add Python Support**
- Still in Extensions, search for **"Python"** and install it
- This gives VS Code superpowers for Python development

**Step 6: Test Everything Works**
- Open the terminal in Visual Studio Code
- Type `python` and press Enter
- If you see Python starting up

![Screenshot of Python in the VS Code Terminal](https://raw.githubusercontent.com/BSMP-Coders/advanced-game-dev/refs/heads/main/img/image.png?token=GHSAT0AAAAAADFYKZPI5WRKV66RMO6TRNF62DIK6KA)

**Step 7: Install Game Libraries** 
- In the terminal, run this magic command:
  ```bash
  pip install -r requirements.txt
  ```
- This installs Pygame and everything else you need.


## 🎲 Choose Your Game Adventure!

Open [main.py](https://github.com/BSMP-Coders/advanced-game-dev/tree/main/lesson-2/main.py) and use these prompts with GitHub Copilot. **Important:** Test your game after each prompt to see your progress!

| 🎮 Game            | 🎯 What You'll Build                                     | 🚀 Step-by-Step Prompts                                                                          |
|--------------------|---------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| **🏓 Pong**        | Classic two-player paddle battle                       | 1. "Create a window and draw two paddles and a ball"<br>2. "Move paddles with keyboard input"<br>3. "Add ball movement and collision detection" |
| **🐍 Snake**       | Control a growing snake to eat food                    | 1. "Draw a snake and food on the screen"<br>2. "Move the snake with arrow keys"<br>3. "Detect collisions with food and self" |
| **🧱 Breakout**    | Bounce a ball to break colorful bricks                 | 1. "Draw a paddle, ball, and a row of bricks"<br>2. "Move the paddle and bounce the ball"<br>3. "Remove bricks when hit by the ball" |
| **🍎 Catch Fruit** | Catch falling fruits with your basket                   | 1. "Draw a basket and falling fruit"<br>2. "Move the basket with keyboard input"<br>3. "Detect when the basket catches the fruit" |

> **💡 Pro Tip:** Don't rush! After each prompt, run your game and see what happens. This is the best way to learn and catch any issues early.

## How to run your game

In the terminal, type the following commands

```bash
cd lesson-2
python main.py
```

## 🔎 Share, Collaborate, and Review in GitHub

 GitHub enables you to work with others and manage projects efficiently through features like Issues, Pull Requests, and Discussions. This is how developers work together to build better software.

In the next activity, you'll practice using GitHub's collaboration tools by sharing your project, trying out a classmate's game, and providing constructive feedback through GitHub Issues. 

### Step 1: Commit & Push Your Game in the Editor
1. Open the Source Control panel in VS Code. You should see your changes listed and an empty message box
1. Type something like: "First version of my Pygame project".
1. Click the Commit button and confirm you see your message in the window.
1. Click "Sync".
1. Verify your code made it to the repository.

### Step 2: Try Someone Else's Game
1. Get your classmate’s GitHub repo link.
1. Open Source Control and Follow the instructions to clone the repository (no need to fork!)
1. Open and test their game 
1. Think about your feedback: What worked well? Any bugs or issues? Suggestions?

### Step 3: Leave Feedback via GitHub Issues
1. On your classmate’s GitHub repo page, click the “Issues” tab → New Issue.
1. In the Description, write out your feedback from step 4.
1. In the Title, summarize the feedback you wrote.
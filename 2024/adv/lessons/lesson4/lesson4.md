# Lesson 4: Introduction to Flask 🚀🌐 <!-- {docsify-ignore-all} -->

Welcome to Lesson 4 of the BSMP24 Advanced Coding Program! In this lesson, we will delve into Flask, a micro web framework for Python. Get ready to build your very own web applications! 🌟

## Objective 🎯

By the end of this lesson, you will:

- Understand the basics of Flask and its role in web development.
- Learn how to set up a simple Flask application.
- Build and modify a Flappy Bird game using Flask and GitHub Copilot.

## Lesson Overview 📖

- **Flask Basics**: Introduction to Flask and its core concepts.
- **Creating a Simple Flask Application**: Step-by-step guide to setting up and running a basic Flask app.
- **Flappy Bird Game with Flask and GitHub Copilot**: Using GitHub Copilot to create and modify a Flappy Bird game.

### Lesson Repo:

* [Lesson 4 Repo](https://classroom.github.com/a/pecBvAwA)

### Lesson 4 Homework:

* **Homework 4**: Create a Flask application that serves a Flappy Bird game. Modify the game based on the activities provided.
* **Homework 4 Due Date**: Thursday 7/18 before the next class.
* [Lesson 4 Homework Link](https://classroom.github.com/a/UGDNcF_L)

## Other Resources 📚

- **Flask Docs**:
  - [Visual Studio Code Flask Tutorial](https://code.visualstudio.com/docs/python/tutorial-flask)
  - [LaunchCode Flask Introduction](https://education.launchcode.org/lchs/chapters/flask-intro/index.html)
  - [LaunchCode First Flask App](https://education.launchcode.org/lchs/chapters/flask-intro/first-flask-app.html)

## Flask Basics Review 📝

Flask is a lightweight, easy-to-use web framework for Python. Let's quickly revisit the core concepts:

### Basic Flask Commands

1. **Setting Up a Flask Server**: Use `Flask` to create a basic web server.

    ```python
    from flask import Flask, request
    import random

    app = Flask(__name__)

    @app.route('/status', methods=['GET'])
    def _live():
        return "Alive!"

    @app.route('/predict', methods=['GET'])
    def predict():
        demo = random.randint(2000, 5000)
        return str(demo)

    app.run(port=5005)
    ```

2. **Running the Flask Server**: Use the terminal to run your Flask application.

    ```sh
    python app.py
    ```

## Building the Flappy Bird Game 🛠️

Let's build a simple Flappy Bird game using Flask and GitHub Copilot.

### Step-by-Step Guide

1. **Set Up Flask Application Structure**: Create the necessary directories and files.

    - `flappybird/`
      - `app.py`
      - `templates/`
        - `index.html`
      - `static/`
        - `style.css`
        - `game.js`

2. **Create Flask Routes**: Set up routes to serve the HTML page and static files.

    ```python
    from flask import Flask, render_template

    app = Flask(__name__)

    @app.route('/')
    def index():
        return render_template('index.html')

    if __name__ == '__main__':
        app.run(debug=True)
    ```

3. **HTML, CSS, and JavaScript for the Game**:
    - **index.html**: Create a canvas element and link the CSS and JavaScript files.
    - **style.css**: Style the game elements.
    - **game.js**: Implement the game logic using JavaScript.

4. **Using GitHub Copilot**:
    - Open your code editor and start typing code.
    - Copilot will provide suggestions, which you can accept by pressing `Tab` or `Enter`.

5. **Modifying the Game**: Use the following activities to modify the game.
    - **Activity 1**: Increase the gap between pipes.
    - **Activity 2**: Reduce the gravity affecting the bird.
    - **Activity 3**: Slow down the speed of the pipes.

## Using GitHub Copilot 🌟

GitHub Copilot can assist you in generating code for your Flask application. Here's a prompt to guide Copilot:

```
Build a Flappy Bird game using Flask as the backend and JavaScript for the frontend. The game should have:
- A canvas element for rendering the game.
- A bird that the player can control with the spacebar.
- Moving pipes that the bird must avoid.
- A scoring system to keep track of the player's score.
```

By providing clear and specific prompts, you can leverage Copilot to write and modify code efficiently.

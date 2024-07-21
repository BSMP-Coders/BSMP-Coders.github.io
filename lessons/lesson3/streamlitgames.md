# Lesson 3/4: Streamlit Games and AI Integration 🎮🤖  

![](https://pbs.twimg.com/media/F80nu7kWYAAjeE7?format=png&name=small)

## Welcome Back Coders!  
   
Welcome to Lesson 3/4 of the BSMP24 Advanced Coding Program! Today's session is all about fun and games – quite literally! We'll be exploring several Streamlit-based games and diving into the process of cloning, setting up, and running a Streamlit game in your coding environment. Plus, we'll touch upon enhancing games with Azure OpenAI. Prepare to level up your coding skills with interactive game development!  
   
## Goals 🎯  
   
- Explore various Streamlit games and understand their mechanics.  
- Learn the process of cloning a game repository and setting it up in GitHub Codespaces.  
- Incorporate Streamlit's interactive elements and Azure OpenAI into your own game for an engaging user experience.  
   
## Lesson Overview 📖  
   
- **Streamlit Game Demos**: Play and analyze StreamlitLand Adventure RPG, Streamlit Dungeon Crawler, and Streamlit Battleships.  
- **Cloning and Running a Game**: Step-by-step guide on how to clone the Battleships game and run it.  
- **Homework - Build Your Own Streamlit Game**: Instructions and requirements for creating your own game with Streamlit and Azure OpenAI integration.  


## Explore Streamlit Game Demos

Start here! Explore some of these game! 🎮🕹️

- [StreamlitLand Adventure RPG](https://github.com/TomJohnH/streamlit-game) 👉 https://adventure.streamlit.app
- [Streamlit Dungeon Crawler](https://github.com/TomJohnH/streamlit-dungeon) 👉 https://dungeon.streamlit.app
- [Streamlit Battleships](https://github.com/shakamoushie/battleships/) 👉 https://battleshipsgame.streamlit.app
- [streamlit galories](https://streamlit.io/gallery?category=favorites)

## Cloning and Running the Battleships Game 🛠️  
   
1. **Git Clone in GitHub Codespaces**: Use the terminal in your existing GitHub Codespace and enter the following command to clone the Battleships repository:  
   ```  
   git clone https://github.com/shakamoushie/Battleships.git  
   ```  
2. **Navigating to the Cloned Repository**: Once the repository is cloned, change your directory by running:  
   ```  
   cd Battleships  
   ```  
3. **Installing Dependencies**: Install the `streamlit_autorefresh` package using pip:  
   ```  
   pip install streamlit_autorefresh  
   ```  
4. **Running the Game**: Launch the game by executing:  
   ```  
   streamlit run battleships.py  
   ```  
   
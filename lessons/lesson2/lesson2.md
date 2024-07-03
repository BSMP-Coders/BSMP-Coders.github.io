# Lesson 2: Mastering If Statements and Loops with Streamlit 🎢  
   
Hello again, budding programmers! It's time to take a thrilling ride through the core concepts of programming: If Statements and Loops. By integrating these with Streamlit, we'll create interactive apps that respond and iterate like never before! 🤩🔄  
   
## Objective 🎯  
   
By the end of this lesson, you'll know how to use if statements and loops to control the flow of your Python programs. You'll also learn how to make your Streamlit apps interactive with buttons and other cool widgets.  
   
## Lesson Overview 📖  
   
- **If Statements**: Learn to guide your code's decisions.  
- **Loops**: Discover how to repeat actions efficiently.  
- **Streamlit Widgets**: See how to add interactivity to your apps.  
   
## Resources You'll Need 📚  
   
Gear up for today's coding challenge with these resources:  

> [!WARNING] <!--[!ATTENTION] ⚠️-->  
> - Your second GitHub repository: [Lesson 2 GitHub Repo](https://github.com/BSMP-Coders/lesson2_streamlit)  
> - Dive into "Python If Statements and Loops" with our Jupyter notebook: [Jupyter Notebook - If Statements & Loops](https://github.com/naivelogic/bam_academy_dev/blob/master/lessons/lesson2.ipynb)  
> - ❌ Try out the interactive activity notebook: [Jupyter Notebook - Lesson 2 Activity](https://github.com/naivelogic/bam_academy_dev/blob/master/lessons/lesson2_activity.ipynb)  
> - ❌ Check out the quick reference: [Lesson 2 Cheatsheet](https://github.com/naivelogic/bam_academy_dev/blob/master/lessons/lesson2_cheatsheet.md)  
   
## If Statements: The Decision Directors 🎬  
   
If statements are the directors of your code's movie, deciding which scenes to play based on certain conditions.  
   
### Using If Statements in Streamlit 🌐  
   
1. Create a button and use an if statement to display a message when it's clicked.  
2. Use checkboxes to capture user preferences and respond with personalized messages.  
   
```python  
like = st.checkbox("Do you like this app?")  
if st.button("Submit"):  
    if like:  
        st.write("Thanks for liking the app!")  
    else:  
        st.write("Aww, we'll try to win your heart next time!")  
```  
   
## Loops: The Repetition Masters 🔄  
   
Loops are the magicians that perform the same trick over and over, saving you from the tedious task of writing repetitive code.  
   
### Experimenting with Loops in Streamlit 🚀  
   
1. Use for loops to display a list of items or repeat actions.  
2. Use while loops to keep an action going until a condition is met.  
   
```python  
for i in range(3):  
    st.write(f"Hello, World! {i+1}")  
```  
   
## Your Coding Mission: If Statements and Loops in Action 🕹️  
   
1. **If Statement Challenge**: Use Streamlit widgets like buttons and checkboxes to create an interactive app that uses if statements to respond to user inputs.  
2. **Loop Challenge**: Implement a simple counter in Streamlit that increments with each button press.  
   
## Ready to Code? 🏁  
   
Armed with if statements and loops, you're about to make your Python programs smarter and your Streamlit apps more dynamic. It's time to code, create, and most importantly, have a blast while doing it!  
   
**Additional Resources:**  
   
For more in-depth tutorials and exercises, be sure to check out these sub-pages:  
   
> [!WARNING] <!--[!ATTENTION] ⚠️-->  
> ### [Python If Statements and Loops Tutorial](https://github.com/BSMP-Coders/lesson2-if-loops-tutorial)  
> Learn the ins and outs of if statements and loops with detailed examples and explanations.  
   
> [!WARNING] <!--[!ATTENTION] ⚠️-->  
> ### [Streamlit Widgets and Interactivity](https://github.com/BSMP-Coders/lesson2-streamlit-widgets)  
> Get hands-on with Streamlit widgets and learn how to make your apps react to user input.  
   
> [!WARNING] <!--[!ATTENTION] ⚠️-->  
> [Return to Lesson 2](https://github.com/BSMP-Coders/lesson2)  
   
**Let's Get Started!** 🌟  
   
Put your thinking cap on and dive into the world of conditional logic and looping constructs. And remember, the best way to learn to code is by doing, so let's get coding!  
   
**Bonus Exploration:** After completing the activities, challenge yourself by combining if statements and loops to create a more complex Streamlit app. Show off your coding chops and impress us with your creativity!
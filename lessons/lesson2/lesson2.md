# Lesson 2: Mastering If Statements and Loops with Streamlit 🎢  
   
Hello again, budding programmers! It's time to take a thrilling ride through the core concepts of programming: If Statements and Loops. By integrating these with Streamlit, we'll create interactive apps that respond and iterate like never before! 🤩🔄  
   
## Objective 🎯  
   
By the end of this lesson, you'll know how to use if statements and loops to control the flow of your Python programs. You'll also learn how to make your Streamlit apps interactive with buttons and other cool widgets.  
   
## Lesson Overview 📖  
   
- **If Statements**: Learn to guide your code's decisions.  
- **Loops**: Discover how to repeat actions efficiently.  
- **Streamlit Widgets**: See how to add interactivity to your apps.  
   
## Additional Resources 📚  
   
For more information on Python if statements and for loops, please go through these tutorials on [vscodeedu - intro to python](https://vscodeedu.com/courses/intro-to-python) using your BAM emails:  
   
- **Unit 3 - If Statements**: [If Statements Tutorial](https://vscode.dev/edu?courseId=intro-to-python&workspace-scheme=vscode-edu-workspace&profile=default#select-course-node=intro-to-python%3Aitp-if)  
- **Unit 5 - For Loops**: [For Loops Tutorial](https://vscode.dev/edu?courseId=intro-to-python&workspace-scheme=vscode-edu-workspace&profile=default#select-course-node=intro-to-python%3Aitp-for)  

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

<details>
<summary>Streamlit Shorts Video: Advanced Widget Techniques</summary>
<p>Explore advanced techniques for using widgets in Streamlit with this tutorial.</p>
<iframe width="560" height="315" src="https://www.youtube.com/embed/JSeQSnGovSE?list=TLGGcen3xq_FouUxMTA3MjAyNA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</details>

<details>
<summary>Streamlit Shorts Video: How to combine a button, checkbox and radio button</summary>
<p>In the video below, learn how to combine a button, checkbox and radio button!</p>
<iframe width="560" height="315" src="https://www.youtube.com/embed/JSeQSnGovSE?list=TLGGcen3xq_FouUxMTA3MjAyNA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</details>

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
   

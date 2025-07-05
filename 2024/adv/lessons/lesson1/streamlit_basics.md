# Streamlit Tutorial  <!-- {docsify-ignore-all} -->
   
Hello future web app developers! This is your step-by-step guide to creating your first web app with Streamlit. Let's dive in! 💻  
   
## What is Streamlit? 🎈  
   
Streamlit is an open-source app framework for Machine Learning and Data Science teams. It turns data scripts into shareable web apps in minutes, all in Python.  
   
## Installing Streamlit 🛠️  
   
If you're using GitHub Codespaces, Streamlit is already installed for you! If not, you can install it using pip:  `pip install streamlit`
   
## Creating Your First App 🌟  
   
Let's create a basic Streamlit app that says hello to the world.  
   
1. Create a new Python file named `app.py`.  
2. Add the following code:  
   
```python  
# Import Streamlit  
import streamlit as st  
   
# Add a title and some text  
st.title("Hello, World!")  
st.write("Welcome to your first Streamlit app. Isn't this fun?")  
```  
   
3. Run your app with:  
   
```sh  
streamlit run app.py  
```  
   
## Adding Interactivity 🕹️  
   
Streamlit lets users interact with your app. Let's add a button!  
   
```python  
if st.button('Say Hello'):  
    st.write('Why hello there!')  
else:  
    st.write('Goodbye')  
```  
   
## Sharing Your App 🌐  
   
Once you're happy with your app, you can share it with others. With GitHub Codespaces, just push your changes to GitHub, and your app is ready to be shared!  
   
Congratulations! 🎉 You've just built and shared your first Streamlit app.  



<details>
<summary>Streamlit Shorts Video: How to create a Streamlit Multi-Page Web App</summary>
<p>Explore in the tutorial how to develop a streamlit multipage web app.</p>
<iframe width="560" height="315" src="https://youtu.be/YClmpnpszq8?si=1RReV9nLyLi3VM1h" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
</details>
# Lesson 3: Streamlit + ChatGPT Integration 🤖💬  
   
Welcome to Lesson 3 of the BSMP24 Advanced Coding Program! Today, we will explore the fascinating world of chatbots by integrating Streamlit with OpenAI's ChatGPT. Get ready to build your very own interactive chat application! 🌟  
   
## Objective 🎯  
   
By the end of this lesson, you will:  
   
- Understand the basics of Streamlit and its role in web app development.  
- Learn about ChatGPT and how to integrate it using OpenAI’s API.  
- Build a simple chat messaging system within Streamlit.  
   
## Lesson Overview 📖  
   
- **Streamlit Basics**: Quick review of what we've learned so far.  
- **ChatGPT Integration**: Setting up and using OpenAI’s API for conversational AI.  
- **Activity**: Create a chat messaging system within Streamlit.  
   
## Resources You'll Need 📚  
   
Before we dive in, make sure you have these resources at your fingertips:  
   
- **Streamlit Conversational Apps Guide**: [Streamlit Conversational Apps Guide](https://docs.streamlit.io/develop/tutorials/llms/build-conversational-apps)  
- **OpenAI API for Beginners**: [OpenAI API for Beginners](https://www.kdnuggets.com/openai-api-for-beginners-your-easy-to-follow-starter-guide)  
- **Lesson 3 Jupyter Notebook**: [Lesson 3 Notebook](https://github.com/naivelogic/bam_academy_dev/blob/master/lessons/lesson3.ipynb)  
- **Lecture Notes**: (Provided by your instructor)  
   
## Streamlit Basics Review 📝  
   
Streamlit is a powerful, user-friendly framework for creating interactive web applications with Python. Let's quickly revisit the core concepts:  
   
### Basic Streamlit Commands  
   
1. **Title and Header**: Use `st.title` and `st.header` to add titles and headers to your app.  
  
    ```python  
    import streamlit as st  
  
    st.title("Welcome to BSMP Coding Class on Streamlit 🤖")  
    st.header("Lesson 3: Streamlit + ChatGPT Integration")  
    ```  
   
2. **Text Input**: Use `st.text_input` to get input from the user.  
  
    ```python  
    name = st.text_input("What's your name?", "John")  
    st.write(f'Hello, {name}!')  
    ```  
   
3. **Display Messages**: Use `st.markdown` to display messages.  
  
    ```python  
    st.markdown("This is a markdown message")  
    ```  
   
## Introduction to ChatGPT and OpenAI API 🤖  
   
### What is ChatGPT?  
   
ChatGPT is a language model developed by OpenAI that can generate human-like text based on the input it receives. It's used for various applications, including chatbots, content creation, and more.  
   
### How to Use OpenAI API  
   
To use OpenAI's ChatGPT, you need to:  
   
1. **Sign Up for an API Key**: Create an account on OpenAI's website and get your API key.  
2. **Install OpenAI Package**: Use pip to install the OpenAI package.  
  
    ```sh  
    pip install openai  
    ```  
   
3. **Set Up Your Environment**: Use environment variables to securely store your API key.  
  
    ```python  
    import os  
    import dotenv  
  
    dotenv.load_dotenv()  
    openai_api_key = os.getenv("OPENAI_API_KEY")  
    ```  
   
4. **Make API Calls**: Use the OpenAI package to interact with the ChatGPT model.  
  
    ```python  
    import openai  
  
    response = openai.Completion.create(  
        engine="text-davinci-003",  
        prompt="Hello, how can I assist you today?",  
        max_tokens=150  
    )  
  
    print(response.choices[0].text)  
    ```  
   
## Building Your Chat Application 🛠️  
   
Let's build a simple chat application using Streamlit and OpenAI's ChatGPT.  
   
### Step-by-Step Guide  
   
1. **Set Up Your Streamlit App**  
  
    Create a new Python file named `app.py`.  
  
    ```python  
    import streamlit as st  
    import openai  
    import os  
    import dotenv  
  
    dotenv.load_dotenv()  
  
    # Fetching API key from environment variables  
    openai_api_key = os.getenv("OPENAI_API_KEY")  
  
    # Initialize chat history  
    if "messages" not in st.session_state:  
        st.session_state.messages = []  
  
    st.title("ChatGPT-like Clone")  
  
    # Display chat messages from history  
    for message in st.session_state.messages:  
        with st.chat_message(message["role"]):  
            st.markdown(message["content"])  
  
    # Accept user input  
    if prompt := st.chat_input("What is up?"):  
        st.session_state.messages.append({"role": "user", "content": prompt})  
        with st.chat_message("user"):  
            st.markdown(prompt)  
  
        # Generate response from OpenAI  
        response = openai.Completion.create(  
            engine="text-davinci-003",  
            prompt=prompt,  
            max_tokens=150  
        ).choices[0].text  
  
        with st.chat_message("assistant"):  
            st.markdown(response)  
  
        st.session_state.messages.append({"role": "assistant", "content": response})  
    ```  
   
2. **Create a .env File**  
  
    Create a `.env` file in the same directory as your `app.py` and add your OpenAI API key:  
  
    ```env  
    OPENAI_API_KEY=your_openai_api_key_here  
    ```  
   
3. **Run Your App**  
  
    Use Streamlit to run your app:  
  
    ```sh  
    streamlit run app.py  
    ```  
   
## In-Class Activity: Build Your Own Chatbot 💬  
   
### Objective  
   
Create a simple Streamlit app that integrates with OpenAI's ChatGPT to respond to user inputs.  
   
### Instructions  
   
1. **Open a new Python script (e.g., `chatbot.py`).**  
2. **Write the following code:**  
  
    ```python  
    import streamlit as st  
    import openai  
    import os  
    import dotenv  
  
    dotenv.load_dotenv()  
  
    # Fetching API key from environment variables  
    openai_api_key = os.getenv("OPENAI_API_KEY")  
  
    # Initialize chat history  
    if "messages" not in st.session_state:  
        st.session_state.messages = []  
  
    st.title("ChatGPT-like Clone")  
  
    # Display chat messages from history  
    for message in st.session_state.messages:  
        with st.chat_message(message["role"]):  
            st.markdown(message["content"])  
  
    # Accept user input  
    if prompt := st.chat_input("What is up?"):  
        st.session_state.messages.append({"role": "user", "content": prompt})  
        with st.chat_message("user"):  
            st.markdown(prompt)  
  
        # Generate response from OpenAI  
        response = openai.Completion.create(  
            engine="text-davinci-003",  
            prompt=prompt,  
            max_tokens=150  
        ).choices[0].text  
  
        with st.chat_message("assistant"):  
            st.markdown(response)  
  
        st.session_state.messages.append({"role": "assistant", "content": response})  
    ```  
   
### Exercise  
   
- Add a subheader using `st.subheader("This is a subheader")`.  
- Add a text input to accept the user's name and display a greeting using `st.write`.  
- Use the [Streamlit Documentation](https://docs.streamlit.io/) to explore and add one more interactive element of your choice.  
   
## Submitting Your Work 📤  
   
Once you have completed the activity, follow the instructions on the Homework page to submit your work. We're excited to see your chatbots in action! 🤖  
   
## Ready, Set, Code! 🏁  
   
You are now equipped with the tools and knowledge to integrate ChatGPT with Streamlit. Let's dive in and create something amazing! 💻  
   
**Additional Resources:**  
   
- [Streamlit Conversational Apps Guide](https://docs.streamlit.io/develop/tutorials/llms/build-conversational-apps)  
- [OpenAI API for Beginners](https://www.kdnuggets.com/openai-api-for-beginners-your-easy-to-follow-starter-guide)  
   
Happy coding! 🎉
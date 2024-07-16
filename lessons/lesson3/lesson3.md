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

### Lesson Repo:

* Lesson 3 Repo: https://classroom.github.com/a/pecBvAwA


### Lesson 3 Homework: 

* **Homework 3**: You will build a Streamlit app that allows users to generate a catchy song hook and a meaningful verse based on their chosen artist and topic.
* **Homework 3 Due Date**: Thursday 7/18 before the next class.
* Lesson 3 Homework Link: https://classroom.github.com/a/UGDNcF_L


## Other Resources 📚  

- **Streamlit Docs**: 
  - [Streamlit Intro to How to build a Chat App](https://youtu.be/4sPnOqeUDmk?si=6JGTKLSrtBkFDUuR) (2 mins - YouTube)
  - [Build a basic LLM chat app](https://docs.streamlit.io/develop/tutorials/llms/build-conversational-apps)
  - [st.chat_message](https://docs.streamlit.io/develop/api-reference/chat/st.chat_message) 
  - [st.chat_input](https://docs.streamlit.io/develop/api-reference/chat/st.chat_input)

- **OpenAI Docs**:
  - [**OpenAI getting started**](https://platform.openai.com/docs/overview)
  - [**Open AI Text Generation Guide**](https://platform.openai.com/docs/guides/text-generation)
  - [**Azure OpenAI API for Beginners**](https://microsoftlearning.github.io/mslearn-openai/Instructions/Exercises/02-natural-language-azure-openai.html)

- **Related Python Fundamentals**: We will go over some of this next week, but if you are interested or want more info on Python fundamentals, we will be touching on i would go through just 
  - [lesson 1-3 of Unit 2 Functions](https://vscode.dev/edu?courseId=intro-to-python&workspace-scheme=vscode-edu-workspace&profile=default#select-course-node=intro-to-python%3Aitp-functions) from vscodeedu
  - [Functions YouTube Basics](https://youtu.be/nrCAxXfRU28?list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6), part [2](https://youtu.be/C9ZEGqGHXms?list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6) and [3](https://youtu.be/9Os0o3wzS_I?list=PLlrxD0HtieHhS8VzuMCfQD4uJ9yne1mE6) from Corey Schafer
   
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
   
## Introduction to ChatGPT and Azure OpenAI API 🌐  
   
ChatGPT is a language model developed by OpenAI that can understand and generate human-like text. We’ll use the Azure OpenAI API to integrate ChatGPT into our Streamlit app.  
   
### Setting Up Azure OpenAI API  
   
1. **Install Required Packages**:  
  
   ```bash  
   pip install openai streamlit python-dotenv  
   ```  
   
   
2. **API Key Setup**: Obtain your API key from Azure and set it up in your app. 
   
   Create a `.env` file in the same directory as your `app.py` and add your OpenAI API key:  
  
    ```env  
    AZURE_OPENAI_ENDPOINT=""
    AZURE_OPENAI_API_KEY="" 
    ```   

   **Initialize the Client**: Use the `AzureOpenAI` class to set up the client for making API calls.
   ```python  
   from openai import AzureOpenAI  
   import os  
   import dotenv  
  
   dotenv.load_dotenv()  
  
   AOAI_ENDPOINT = os.getenv("AZURE_OPENAI_ENDPOINT")  
   AOAI_KEY = os.getenv("AZURE_OPENAI_API_KEY")  
  
   client = AzureOpenAI(  
       api_key=AOAI_KEY,  
       azure_endpoint=AOAI_ENDPOINT,  
       api_version="2024-05-01-preview",  
   )  
   ```  
   
3. **Making API Calls**: Use the `client.chat.completions.create` method to generate responses.  
  
   ```python  
   response = client.chat.completions.create(  
       model="gpt-35-turbo",  
       messages=[  
           {"role": "user", "content": "Hello, how can I help you?"}  
       ],  
       stream=False,  
   )  
   reply = response.choices[0].message.content
   ``` 
   
## Building Your Chat Application 🛠️  
   
Let's build a simple chat application using Streamlit and OpenAI's ChatGPT.  
   
### Step-by-Step Guide  
   
1. **Set Up Your Streamlit App**  
  
    Create a new Python file named `app.py`.  
  
    ```python  
    from openai import AzureOpenAI
    import os  
    import streamlit as st  
    import dotenv
    dotenv.load_dotenv()
        
    # Put the keys and variables here (never put your real keys in the code)  
    AOAI_ENDPOINT = os.environ["AZURE_OPENAI_ENDPOINT"]  
    AOAI_KEY = os.environ["AZURE_OPENAI_API_KEY"]  
    MODEL_NAME = "gpt-35-turbo"  

    # Set up the client for AI Chat  
    client = AzureOpenAI(api_key=AOAI_KEY,azure_endpoint=AOAI_ENDPOINT,api_version="2024-05-01-preview",)

    st.subheader("Our First ChatGPT-like app")  

    # Initialize session state for storing messages
    if "messages" not in st.session_state:  
        st.session_state.messages = []  
        #st.session_state.messages = [{"role": "system", "content": "You are a helpful assistant that responds like a pirate."}]

    # Create a button to reset the conversation
    if st.button("New Topic"):        
        #st.session_state.messages = []  
        st.session_state.messages = [{"role": "system", "content": "You are a helpful assistant that responds like a pirate."}]

    # Display all previous messages
    for message in st.session_state.messages:  
        with st.chat_message(message["role"]):  
            st.markdown(message["content"])  

    # Get user input and generate a response
    user_input = st.chat_input("What is up?")
    if user_input:  
        st.session_state.messages.append({"role": "user", "content": user_input})  
        with st.chat_message("user"):  
            st.markdown(user_input)  
        with st.chat_message("assistant"):  
            response = client.chat.completions.create(  
                model=MODEL_NAME,  
                messages=st.session_state.messages,  
                stream=False
            )
            response_content = response.choices[0].message.content  
            st.markdown(response_content)  
            st.session_state.messages.append({"role": "assistant", "content": response_content})
    ```  
   
2. **Create a .env File**  
  
    Create a `.env` file in the same directory as your `app.py` and add your OpenAI API key:  
  
    ```env  
    AZURE_OPENAI_ENDPOINT=""
    AZURE_OPENAI_API_KEY="" 
    ```  
   
3. **Run Your App**  
  
    Use Streamlit to run your app:  
  
    ```sh  
    streamlit run app.py  
    ```  
   

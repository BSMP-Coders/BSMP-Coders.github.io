<!-- /lessons/lesson5/lesson5_intro.md-->  
# Lesson 5: Creating an AI-Driven Flask Web App 🚀  

> [!LESSON_REPO]
>
> Refer to this <i class="fab fa-github"></i> [Lesson Repository](https://github.com/BSMP-Coders/advanced-course-2024/tree/master/lesson5) for lesson details and activities for this lesson.


-----


Welcome to Lesson 5, young coders! Today, we're going to combine the power of Python, Flask, and Azure's OpenAI to create an AI-driven web application. By the end of this lesson, you'll have built a Flask web app that can interact with users and provide intelligent responses using Azure's AI. Let's get started on building your own AI assistant! 🤖✨  
   
## Objective 🎯  
   
The goal of this lesson is to introduce you to building web applications with Flask and integrating AI capabilities using Azure OpenAI. You'll learn how to set up a Flask server, handle HTTP requests, and communicate with an AI model to provide smart autocomplete suggestions.  
   
## Lesson Overview 📖  
   
- **Flask Web Framework**: Dive into the Flask web framework and learn how to set up a simple server.  
- **Azure OpenAI Integration**: Discover how to connect your Flask app to Azure's OpenAI service.  
- **Building an AI Assistant**: Create an autocomplete feature that provides suggestions as you type.  
   
## Resources You'll Need 📚  
   
Make sure to have the following resources accessible for a smooth coding experience:  
   
- The Flask and OpenAI lesson repository: [Lesson 5 GitHub Repo](https://github.com/BSMP-Coders/lesson5_flaskgpt)  
- Access the Lesson 5 invite in GitHub Classroom: [GitHub Classroom Invite](https://classroom.github.com/a/KddoilYB)  
- Review the Flask client notebook to understand how requests are sent and handled: [Flask Client Notebook](https://github.com/orhannurkan/Flask_server_in_Jupyter)  
- Explore the Flask server notebook to see how the server processes requests: [Flask Server Notebook](https://github.com/Azure-Samples/simple-flask-server-appservice)  
   
## Flask: Your Gateway to Web Applications 🌐  
   
Flask is a lightweight and easy-to-use web framework for Python. It allows you to create web applications quickly and with minimal code.  
   
### Setting Up Your Flask Server 🛠️  
   
1. Create a new Flask application by defining a Flask instance.  
2. Set up routes to handle different types of requests.  
3. Run the server and test it to ensure it's working properly.  
   
```python  
from flask import Flask  
app = Flask(__name__)  
   
@app.route('/')  
def home():  
    return "Welcome to the AI-Driven Flask Web App!"  
   
if __name__ == '__main__':  
    app.run(debug=True)  
```  
   
## Azure OpenAI: Supercharging Your App with AI 🧠  
   
Azure OpenAI provides access to powerful AI models like GPT-3.5. You'll learn how to use these models to generate human-like text based on user input.  
   
### Integrating Azure OpenAI with Flask 🔌  
   
1. Set up the Azure OpenAI client with your API key and endpoint.  
2. Create a function that sends prompts to OpenAI and receives suggestions.  
3. Use this function to provide autocomplete suggestions in your web app.  
   
```python  
from openai import AzureOpenAI  
   
# Initialize the Azure OpenAI client  
openai_client = AzureOpenAI(api_key='your_api_key', azure_endpoint='https://your-endpoint.openai.azure.com/')  
   
# Function to get suggestions from OpenAI  
def get_suggestions(prompt):  
    response = openai_client.chat.completions.create(  
        model="gpt-35-turbo",  
        messages=[  
            {"role": "system", "content": "You are an autocomplete assistant."},  
            {"role": "user", "content": prompt}  
        ],  
        temperature=0.5  
    )  
    return response.choices[0].message.content  
```  
   
## Building Your AI Assistant 🤖  
   
You will create an interactive web application that uses your Flask server and Azure OpenAI to provide smart autocomplete suggestions.  
   
### Activity: Develop an Autocomplete Web App 🖥️  
   
1. Set up a simple HTML form that allows users to type input.  
2. Use JavaScript to capture input and send it to your Flask server via AJAX.  
3. Display the AI-generated suggestions on the web page in real time.  
   
## Submitting Your Work 📤  
   
Once you've completed your AI-driven Flask web app, submit your work through the GitHub Classroom link provided. We're excited to see your creative applications!  
   
## Ready, Set, Code! 🏁  
   
It's time to bring your AI assistant to life! Follow the steps, write the code, and remember to have fun while learning. Coding is not just about solving problems; it's also about creating new possibilities. So let's innovate and create something amazing together!  
   
**Additional Resources:**  
   
For a more comprehensive guide and examples, check out these helpful pages:  
   
### [Flask Server and Client Examples](https://github.com/BSMP-Coders/lesson5_flaskgpt-examples)  
An in-depth look at how to set up Flask servers and clients, with example code.  
   
### [Azure OpenAI Documentation](https://docs.microsoft.com/en-us/azure/cognitive-services/openai/)  
Detailed documentation on how to use Azure OpenAI services.  
   
> [!WARNING] <!--[!ATTENTION] ⚠️-->  
> [Return to Lesson 5](https://github.com/BSMP-Coders/lesson5_flaskgpt)  
   
**Let's Dive In!** 🌊  
   
With Flask as your server-side companion and Azure OpenAI as your AI partner, you're ready to build an app that's not only functional but also intelligent. Let's code and see where your imagination takes you!  
   
**Bonus Exploration:** After you've built the autocomplete feature, think of other creative ways you can use AI in your web applications. The possibilities are endless!
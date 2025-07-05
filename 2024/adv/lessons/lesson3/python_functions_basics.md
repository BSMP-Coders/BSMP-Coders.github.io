# Introduction to Python Functions  
   
## Overview  
In this lesson, we'll cover the basics of Python functions. Functions are a fundamental building block in Python, allowing you to encapsulate code into reusable blocks. We'll also demonstrate how to use the `generate_response` function from our previous lesson on Azure OpenAI.  
   
## What is a Function?  
A function is a block of code which only runs when it is called. You can pass data, known as parameters, into a function. A function can return data as a result.  
   
### Basic Function Syntax  
```python  
def function_name(parameters):  
    """docstring"""  
    # Function body  
    return result  
```  
   
- `def`: Keyword to define a function.  
- `function_name`: Name of the function.  
- `parameters`: Optional. A list of parameters that the function can accept.  
- `"""docstring"""`: Optional. A string that describes what the function does.  
- `return`: Optional. Used to return a value from the function.  
   
### Example: Simple Function  
```python  
def greet(name):  
    """This function greets the person passed in as a parameter."""  
    return f"Hello, {name}!"  
   
# Calling the function  
print(greet("Alice"))  # Output: Hello, Alice!  
```  
   
## Using `generate_response` Function  
   
Let's take a look at the `generate_response` function from our previous lesson and understand its components.  
   
### Function Definition  
```python  
def generate_response(prompt, model="gpt-35-turbo"):  
    response = client.chat.completions.create(  
        model=model,  
        messages=[{"role": "user", "content": prompt}]  
    )  
    return response.choices[0].message.content  
```  
   
- **Function Name**: `generate_response`  
- **Parameters**:  
  - `prompt`: The text input provided by the user.  
  - `model`: The language model to be used (default is `"gpt-35-turbo"`).  
- **Function Body**: Calls the Azure OpenAI API to generate a response based on the prompt.  
- **Return Value**: The content of the response message.  
   
### Calling the Function  
To use the `generate_response` function, you simply call it with the required `prompt` argument. You can also specify the `model` argument if you want to use a different model.  
   
```python  
# Example usage of the function  
print(generate_response("Who is the quarterback for the Dallas Cowboys?"))  
```  
   
## Creating Your Own Functions  
   
### Example: Addition Function  
Let's create a simple function that adds two numbers.  
   
```python  
def add_numbers(a, b):  
    """This function adds two numbers and returns the result."""  
    return a + b  
   
# Calling the function  
result = add_numbers(5, 3)  
print(f"The sum is: {result}")  # Output: The sum is: 8  
```  
   
### Example: Temperature Converter  
Now, let's create a function that converts Celsius to Fahrenheit.  
   
```python  
def celsius_to_fahrenheit(celsius):  
    """This function converts Celsius to Fahrenheit."""  
    return (celsius * 9/5) + 32  
   
# Calling the function  
fahrenheit = celsius_to_fahrenheit(25)  
print(f"25 degrees Celsius is {fahrenheit} degrees Fahrenheit.")  # Output: 25 degrees Celsius is 77.0 degrees Fahrenheit.  
```  
   
## Conclusion  
Functions are a powerful feature in Python that allow you to write reusable and modular code. By defining functions, you can break down complex problems into smaller, manageable pieces. Practice creating your own functions to become more comfortable with this concept.  
   
For more advanced topics and further exploration, consider integrating functions with libraries like Azure OpenAI to build sophisticated applications.  
   
Happy coding!
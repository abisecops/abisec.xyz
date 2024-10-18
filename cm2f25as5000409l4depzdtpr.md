---
title: "SSTI Code Review Lab 2"
seoTitle: "SSTI Code Lab Essentials"
seoDescription: "Learn to set up an SSTI code review lab, understand vulnerabilities, and apply prevention techniques for secure application development"
datePublished: Fri Oct 18 2024 18:22:53 GMT+0000 (Coordinated Universal Time)
cuid: cm2f25as5000409l4depzdtpr
slug: ssti-code-review-lab-2
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729274644301/323e1ee6-a97f-45a3-99c7-91fe88c7e8b6.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1729275757343/8f391684-9820-4cfd-b7ee-020459c26017.png
tags: code-review, web-development, hacking, pentesting, server-side-template-injection

---

### Lab Setup

1. Create a folder for the challenge.
    
    ```bash
     mkdir ssti_ctf1_challenge
     cd ssti_ctf1_challenge
    ```
    
2. Set up the environment
    
    ```bash
     python3 -m venv venv
     source venv/bin/activate 
     pip install Flask
    ```
    
3. Create [`app.py`](http://app.py)
    
    ```python
    from flask import Flask, request, render_template_string
    
    app = Flask(__name__)
    
    @app.route('/')
    def index():
        return '''
            <h1>Welcome to the SSTI Code Review Lab 2!</h1>
            <form method="POST" action="/submit">
                <table>
                    <tr>
                        <td><label for="name">Name:</label></td>
                        <td><input type="text" id="name" name="name" placeholder="Enter your name" required /></td>
                    </tr>
                    <tr>
                        <td><label for="feedback">Feedback:</label></td>
                        <td><input type="text" id="feedback" name="feedback" placeholder="Enter your feedback" required /></td>
                    </tr>
                    <tr>
                        <td colspan="2" style="text-align: center;">
                            <input type="submit" value="Submit" />
                        </td>
                    </tr>
                </table>
            </form>
        '''
    
    @app.route('/submit', methods=['POST'])
    def submit():
        name = request.form['name']
        feedback = request.form['feedback']
    
        # Vulnerable to SSTI: directly rendering user input without sanitization
        template = f'''
            <h1>Hello, {name}!</h1>
            <p>Your feedback: {feedback}</p>
            <p>Try injecting a template expression!</p>
        '''
        return render_template_string(template)
    
    if __name__ == '__main__':
        app.run(debug=True)
    ```
    
4. Run the Application
    
    ```bash
     python app.py
    ```
    
5. We now have our web app ready.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729274703025/1397d225-e422-4660-858a-9ed7172c6caa.png align="left")
    
6. Try the `SSTI payload now` and submit:
    
    \- `{{ 7*7 }}`
    
    \- {{config}}
    
    * I am using `{{ 7*7 }}` for Name and `{{5*5}}` for Feedback
        
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729274220828/d003e296-a091-477f-bcaf-44448943edc8.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729274393866/7587ed39-ce23-40e2-9a04-34b919909ef5.png align="center")
    
7. Now, we can see our `SSTI payload` is working correctly.
    
    Let me try this payload `{{config}}` in the feedback now.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729274439606/58cd4b93-600c-4e3f-a17a-2e9a55237f33.png align="center")
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729274495367/3f7ab22b-8e2d-4845-88d3-6f3725325f17.png align="left")
    
    ### **Causes of this vulnerability**
    
    1. **F-String Usage:** Directly using f-strings to interpolate user input into the template, allowing code execution.
        
    2. **No Input Validation:** User input is not validated or sanitized before rendering.
        
    3. **Raw Template Rendering:** Using `render_template_string` with unescaped user input.
        
    4. **Lack of Escaping Mechanisms:** Failing to utilize escaping functions to prevent injection attacks.
        
    5. **Assuming User Input is Safe:** Trusting user input without proper checks leads to vulnerabilities.
        

### **Code Review**

1. Vulnerable code
    
    ```python
        template = f'''
            <h1>Hello, {name}!</h1>
            <p>Your feedback: {feedback}</p>
            <p>Try injecting a template expression!</p>
        '''
        return render_template_string(template)
    ```
    
2. Prevention Code
    
    * Use `render_template` instead of `render_template_string` to automatically escape user input.
        
        ```python
        from flask import render_template
        
        @app.route('/submit', methods=['POST'])
        def submit():
            name = request.form['name']
            feedback = request.form['feedback']
            return render_template('response.html', name=name, feedback=feedback)
        ```
        
    * Use html page instead of fstring. Do not use f-strings or similar methods for rendering user input directly.
        
        ```python
        # Avoid this:
        template = f'''
            <h1>Hello, {name}!</h1>
        '''
        ```
        
    * We can also use the built-in `escape` function to clean user input before rendering. If the above prevention method is not followed.
        
        ```python
        from flask import escape
        
        @app.route('/submit', methods=['POST'])
        def submit():
            name = escape(request.form['name'])
            feedback = escape(request.form['feedback'])
            template = f'''
                <h1>Hello, {name}!</h1>
                <p>Your feedback: {feedback}</p>
            '''
            return render_template_string(template)
        ```
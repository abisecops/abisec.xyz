---
title: "SSTI CTF Challenge 1"
seoTitle: "SSTI CTF Challenge Overview"
seoDescription: "Learn about SSTI vulnerabilities with a Capture The Flag challenge, understand causes, and explore code prevention techniques"
datePublished: Thu Oct 17 2024 17:03:24 GMT+0000 (Coordinated Universal Time)
cuid: cm2djv7ub000b09l87x0p2ybj
slug: ssti-ctf-challenge-1
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1729184244796/c375ac30-e2c6-444a-adf5-4f90b5836642.png
ogImage: https://cdn.hashnode.com/res/hashnode/image/upload/v1729184582984/cf0e2369-de19-4bef-ad8e-976d278b55e3.png
tags: code-review, python, hacking, flask, server-side-rendering, web-security

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
            <h1>Welcome to the SSTI CTF Challenge!</h1>
            <form method="POST" action="/submit">
                <input type="text" name="user_input" placeholder="Enter your name" />
                <input type="submit" value="Submit" />
            </form>
        '''
    
    @app.route('/submit', methods=['POST'])
    def submit():
        user_input = request.form['user_input']
        # Intentionally vulnerable: rendering user input directly in the template
        template = f'''
            <h1>Hello, {user_input}!</h1>
            <p>Your input has been rendered. Try to exploit it!</p>
        '''
        return render_template_string(template)
    
    if __name__ == '__main__':
        app.run(debug=True)
    ```
    
4. Run the Application
    
    ```python
    python app.py
    ```
    
5. We now have our web app ready.
    
6. ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729183333492/944a0c61-eecd-4966-ba10-307b5d02a103.png align="center")
    
    Try the `SSTI payload now` and submit:
    
    \- `{{ 7*7 }}`
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729183433986/d9b2323f-42dc-4563-b815-c88c81905b6f.png align="center")
    
7. Now we can see that we get 49, which means our SSTI payload is working.
    
    ![](https://cdn.hashnode.com/res/hashnode/image/upload/v1729183464521/4cb6da35-ff00-4de7-855b-c36cfe5a7947.png align="center")
    
    ### Causes of this vulnerability
    
    1. **Direct Rendering**: User input is directly rendered in the template with f-strings, allowing attackers to use template syntax.
        
    2. **Lack of Validation/Sanitization**: No validation or escaping of `user_input` lets attackers inject harmful payloads.
        

### Code Review

1. Vulnerable code
    
    ```python
      user_input = request.form['user_input']
        # Vulnerable to SSTI: directly rendering user input
        template = f'''
            <h1>Hello, {user_input}!</h1>
            <p>Your input has been rendered. Try to exploit it!</p>
    ```
    
2. Prevention Code
    

* Use the built-in escape function for user input.
    
* Avoid rendering user input directly.
    

```python
 user_input = request.form['user_input']
safe_input = escape(user_input) 
template = f'''
    <h1>Hello, {safe_input}!</h1>
'''
```

#hacking #securecodereview #ssti #happyhacking
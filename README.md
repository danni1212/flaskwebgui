# flaskwebgui
Freeze web apps made in Flask as desktop apps with flaskwebgui and pyinstaller 

### Install
```
pip install flaskwebgui
```
### Usage
```
from flask import Flask  
from flaskwebgui import FlaskUI #get the FlaskUI class


app = Flask(__name__)
ui = FlaskUI(app) # Feed it the flask app instance


# do your logic as usual in Flask

@app.route("/")
def index():  
    return "It works!"


ui.run() # call the 'run' method from the FlaskUI instance
 
```
### Configurations

Default FlaskUI class parameters: 

        * app,                              ==> flask  class instance
        * browser_name="chrome",            ==> name of the browser "chrome" or "firefox"
        * browser_path="",                  ==> full path to browser exe, ex: "C:/browser_folder/chrome.exe"
        * localhost="http://127.0.0.1:5000" ==> specify other if needed
        * executable_name                   ==> the executable "main.py" will be "main.exe" after freezing (needed to close the exe)
        * width=800                         ==> default width 800 
        * height=600                        ==> default height 600

<br>
You can use a portable version of Chrome!
<br>
Download Chromium portable from -> https://chromium.woolyss.com/
<br>
Place the portable Chromium app next to main.py file.
<br>

### Distribution

```
pyinstaller main.py

```
You can distribute it with [pyvan](https://github.com/ClimenteA/pyvan) also.


### Credits

It's a combination of https://github.com/Widdershin/flask-desktop and https://github.com/ChrisKnott/Eel
<br>
flaskwebgui just uses threading to start a flask server and the browser in app mode (for chrome)
<br>
It has some advantages over flask-desktop because it doesn't use PyQt5, so you won't have any issues regarding licensing and over Eel because you don't need to learn any logic other than Flask.










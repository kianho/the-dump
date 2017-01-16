# Python
```python
import os
import sys

from flask import Flask, request
from yattag import Doc, indent

APP = Flask(__name__)

@APP.route("/static/<path:path>")
def static_file(path):
    return APP.send_static(path)
    

@APP.route("/")
def run():
    """
    """
    doc, tag, text = Doc().tagtext()
    
    with tag("head"):
        with tag("script", src="/static/js/script.js"):
            pass

    return indent(doc.getvalue())


if __name__ == '__main__':
    APP.run(host="localhost", debug=True, port=8888)
```

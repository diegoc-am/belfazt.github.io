---
layout: post
title:  "Building an URL shortener in Python"
categories: technology python
---

A while ago I decided to build an URL shortener in Python, I don't think is the best implementation or the best technology to build one, I just thought that it would be cool to write down my thoughts.

#### Make sure to have the following before starting

* [python](https://www.python.org/)
* [virtualenv](https://virtualenv.pypa.io/en/stable/)

I'll be using python 2.7.14, probably any 2.7.x version works, if you burn your computer it's not my fault

### Generate a virtual env

```bash
# This will help us so that we don't install the dependencies system-wide
virtualenv venv
source venv/bin/activate
```

### Get flask

```bash
pip install flask
```

## Let's code!

We will start by doing the most basic example, a Hello World

```python
# app/shortener.py
from flask import Flask
app = Flask(__name__)

@app.route('/')
def hello():
    return 'Hello World!'

# We set the mode to debug so that if we modify the file it will autoreload the server
# and will display a nice backtrace if what we wrote doesn't make sense
if __name__ == '__main__':
    app.run(debug=True)
```

Afterwards we can run a `curl` to verify that what we wrote works correctly

```bash
curl localhost:5000
# Hello World!%
```


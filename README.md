Flask-SocketIO
==============

Socket.IO integration for Flask applications.

Installation
------------

Install as usual with pip into a venv:

    (venv)$ pip install flask-socketio

Example
-------

```py
from flask import Flask, render_template
from flask_socketio import SocketIO, emit
    
app = Flask(__name__)
app.config['SECRET_KEY'] = 'secret!'
socketio = SocketIO(app)

@app.route('/')
def index():
    return render_template('index.html')

@socketio.on('my event')
def test_message(message):
    emit('my response', {'data': 'got it!'})

if __name__ == '__main__':
    socketio.run(app)
```

Resources
---------

- [Tutorial_1: Medium article](https://levelup.gitconnected.com/flask-socket-io-launch-your-own-webserver-with-realtime-messaging-a703d059be48)
- [Tutorial_2: Miguel Grinberg](http://blog.miguelgrinberg.com/post/easy-websockets-with-flask-and-gevent)
- [Documentation](http://flask-socketio.readthedocs.io/en/latest/)
- [PyPI](https://pypi.python.org/pypi/Flask-SocketIO)
- [Change Log](https://github.com/miguelgrinberg/Flask-SocketIO/blob/master/CHANGES.md)
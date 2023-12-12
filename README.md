# webSiteServ_with_waitress_pkg
# https://nagasudhir.blogspot.com/2022/10/waitress-as-flask-server-wsgi.html
from flask import Flask
from waitress import serve

app = Flask(__name__)

@app.route('/')
def index():
    return 'Hello, World with waitress!!!'

mode = "dev"

if __name__ == '__main__':
    if mode == "dev":
        app.run(host='0.0.0.0', port=50100, debug=True)
    else:
        serve(app, host='0.0.0.0', port=50100, threads=1)

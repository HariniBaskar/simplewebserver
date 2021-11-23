# Developing a Simple Webserver
## AIM:
### To develop a simple webserver to display the top five programming languages.

## DESIGN STEPS:
## Step 1: 
### HTML content creation
## Step 2:
### Design of webserver workflow
## Step 3:
### Implementation using Python code
## Step 4:
### Serving the HTML pages.
## Step 5:
### Testing the webserver

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Python</h1>
<h1>Java</h1>
<h1>JavaScript</h1>
<h1>SQL</h1>
<h1>Swift</h1>
</body>
</html>
"""
class myhandler(BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())
server_address = ('',8080)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()
```
## OUTPUT:

## CLIENT SIDE OUTPUT:
![OUTPUT 1](./images/OUTPUT1.png)

## SERVER SIDE OUTPUT:
![OUTPUT 2](./images/OUTPUT2.png)

## RESULT:
### To develop a simple webserver to display the top five programming languages is executed successfully.
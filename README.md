# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages and display the list of protocols in TCP/IP Protocol Suite.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Import the necessary modules.

### Step 5:
Define a custom request handler.

### Step 6:
Start an HTTP server on a specific port.

### Step 7:
Run the Python script to serve web pages.

### Step 8:
Serve the HTML pages.

### Step 9:
Start the server script and check for errors.

### Step 10:
Open a browser and navigate to http://127.0.0.1:8000 (or the assigned port).

## PROGRAM:
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>My Colored Webpage</title>
    <style>
        body {
            background-color: lightblue; /* Sets the background color */
            text-align: center; /* Centers the text */
            font-family: Arial, sans-serif;
        }
    </style>
</head>
<body>
    <h1>Welcome to My Website</h1>
    <p>This is a simple webpage with a background color.</p>
    <a href="https://www.google.com" target="_blank">Visit Google</a>
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
server_address = ('',80)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

```



## OUTPUT:
![Screenshot 2025-03-11 113904](https://github.com/user-attachments/assets/b3c60089-bf48-44b8-b280-f4b00ab178d2)
![Screenshot 2025-03-11 113959](https://github.com/user-attachments/assets/fa1556fe-99ee-4c99-bb8a-ed32451bde7b)






## RESULT:
The program for implementing simple webserver is executed successfully.


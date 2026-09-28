# SImpleWEBSever
# EX01 Developing a Simple Webserver
## Date:28.09.2026

## AIM:
To develop a simple webserver to serve html pages and display the Device Specifications of your Laptop.

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
...
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<title>My Webserver</title>
</head>

<body>

<h1>Student Details</h1>

<p><b>Name:</b> SYED ABDUL RAZZAQ S</p>
<p><b>Register Number:</b> 26009952</p>

<h2>Laptop Specifications</h2>

<p><b>Name:</b> Acer (TL15-53M-G2)</p>
<p><b>Processor:</b> Intel(R) Core(TM) 5 210H (2.20 GHz)</p>
<p><b>RAM:</b> 16GB</p>
<p><b>Storage:</b> 477 GB</p>
<p><b>OS:</b> Windows 11 Home Single Language</p>

</body>
</html>
"""

class myhandler (BaseHTTPRequestHandler):
    def do_GET(self):
        print("request received")
        self.send_response(200)
        self.send_header('content-type', 'text/html; charset=utf-8')
        self.end_headers()
        self.wfile.write(content.encode())

server_address = ('',8000)
httpd = HTTPServer (server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()
from http.server import HTTPServer, BaseHTTPRequestHandler

content = """
<!DOCTYPE html>
<html>
<head>
<title>Laptop Specifications</title>
</head>
<body>
<h1>Laptop Specifications</h1>

<p><strong>Name:</strong> SYED ABDUL RAZZAQ</p>
<p><strong>Register Number:</strong> 26009952</p>

<h2>Laptop Details</h2>
<p><strong>Name:</strong> Acer (TL15-53M-G2)</p>
<p><strong>Processor:</strong> Intel(R) Core(TM) 5 210H (2.20 GHz)</p>
<p><strong>RAM:</strong> 16GB</p>
<p><strong>Storage:</strong> 477 GB</p>
<p><strong>OS:</strong> Windows 11 Home Single Language</p>

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

server_address = ('', 8000)
httpd = HTTPServer(server_address, myhandler)
print("my webserver is running...")
httpd.serve_forever()
...

## OUTPUT:

![alt text](<Screenshot 2026-09-28 211918.png>)

![alt text](<Screenshot 2026-09-28 212330.png>)




## RESULT:
The program for implementing simple webserver is executed successfully.

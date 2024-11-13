# EX01 Developing a Simple Webserver
## Date:09\10\2024

## AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

## DESIGN STEPS:
### Step 1: 
HTML content creation.

### Step 2:
Design of webserver workflow.

### Step 3:
Implementation using Python code.

### Step 4:
Serving the HTML pages.

### Step 5:
Testing the webserver.

## PROGRAM:
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """"
<html>
    <body bgcolor="violet">
    <h1 align="center">LAPTOP PROPERTY(Trisha-24008628)</h1>
   <ol>
<li>Device name	Trisha</li>
<li>Processor	13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</li>
<li>Installed RAM	16.0 GB (15.7 GB usable)</li>
<li>Device ID	15EEA3B2-7EF5-4DEC-903D-577382C3C005</li>
<li>Product ID	00342-42709-07059-AAOEM</li>
<li>System type	64-bit operating system, x64-based processor</li>
<li>Pen and touch No pen or touch input is available for this display</li>
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
server_address = ('',8000)
httpd = HTTPServer(server_address,myhandler)
print("my webserver is running...")
httpd.serve_forever()

## OUTPUT:

## RESULT:
The program for implementing simple webserver is executed successfully.

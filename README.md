# EX01 Developing a Simple Webserver
## Date:07.10.2025

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>TCP/IP Protocol Table</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      margin: 40px;
      background-color: #f4f4f4;
    }
    h1 {
      text-align: center;
    }
    table {
      width: 80%;
      margin: auto;
      border-collapse: collapse;
      background-color: #fff;
    }
    th, td {
      border: 1px solid #ccc;
      padding: 12px;
      text-align: center;
    }
    th {
      background-color: #007BFF;
      color: white;
    }
    tr:nth-child(even) {
      background-color: #f2f2f2;
    }
  </style>
</head>
<body>
  <h1>TCP/IP Protocol Suite</h1>
  <table>
    <tr>
      <th>Layer</th>
      <th>Protocols</th>
      <th>Examples</th>
    </tr>
    <tr>
      <td>Application</td>
      <td>HTTP, FTP, SMTP, DNS</td>
      <td>Web browsing, Email, File transfer</td>
    </tr>
    <tr>
      <td>Transport</td>
      <td>TCP, UDP</td>
      <td>Reliable delivery, Streaming</td>
    </tr>
    <tr>
      <td>Internet</td>
      <td>IP, ICMP, ARP</td>
      <td>Routing, Addressing</td>
    </tr>
    <tr>
      <td>Network Access</td>
      <td>Ethernet, Wi-Fi</td>
      <td>Physical transmission</td>
    </tr>
  </table>
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
```

## OUTPUT:
<img width="1613" height="401" alt="image" src="https://github.com/user-attachments/assets/a452605a-a011-4b89-9db4-9e1c91644447" />
<img width="818" height="322" alt="image" src="https://github.com/user-attachments/assets/8ea90472-a5d7-417a-8d70-935f39e089b2" />


## RESULT:
The program for implementing simple webserver is executed successfully.

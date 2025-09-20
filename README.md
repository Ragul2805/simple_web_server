# EX01 Developing a Simple Webserver

# Date:19-09-2025
# AIM:
To develop a simple webserver to serve html pages and display the configuration details of laptop.

# DESIGN STEPS:
## Step 1:
HTML content creation.

## Step 2:
Design of webserver workflow.

## Step 3:
Implementation using Python code.

## Step 4:
Serving the HTML pages.

## Step 5:
Testing the webserver.

# PROGRAM:
```
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
<head>
<title> My web server</title>
</head>
<body><center>
    <h1>TCP/IP Protocol Suite</h1>
    <table border="5" cell panding="1" align="center">
        <tr>
            <th>TCP/IP Layer</th>
            <th>Key Protocols</th>
       </tr>
       <tr>
            <td>Application Layer</td>
            <td>HTTP, FTP, SMTP, DNS,</td>
       </tr>
       <tr>
            <td>Transport Layer</td>
            <td>TCP, UDP</td>
       </tr>
       <tr>
            <td>Internet Layer</td>
            <td>IP (IPv4, IPv6), ICMP, ARP</td>
       </tr>
       <tr>
            <td>Network Access Layer</td>
            <td>Ethernet, Wi-Fi (IEEE 802.11), PPP</td>
       </tr>
    </table>
</center>
</body>
</html>
'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received...")
        self.send_response(200) 
        self.send_header("content-type", "text/html")       
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver") 
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()

```

# OUTPUT:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/89ddd3b6-b48a-4514-8f10-fe5be25bf086" />

<img width="1098" height="311" alt="image" src="https://github.com/user-attachments/assets/4ff96791-b01e-4ad1-8e60-df4e34db46db" />



# RESULT:
The program for implementing simple webserver is executed successfully.

# EX01 Developing a Simple Webserver

# Date:
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
```from http.server import HTTPServer,BaseHTTPRequestHandler
content ='''<!DOCTYPE html>
<html>
<head>
    <title>TCP/IP Protocol Suite</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            padding: 20px;
            background-color: #0a0008;
            display: flex;
            flex-direction: column;
            align-items: center;
        }

        h1 {
            color: #fbfb96;
            text-align: center;
        }

        table {
            width: 80%;
            max-width: 800px;
            border-collapse: collapse;
            margin-top: 20px;
            background-color: #d7a484;
        }

        th, td {
            border: 1px solid #0b0000;
            padding: 12px;
            text-align: left;
            vertical-align: top;
        }

        th {
            background-color: #bfddbc;
            color: rgb(19, 1, 1);
        }

        tr:nth-child(even) {
            background-color: #d0d8b7;
        }
    </style>
</head>
<body>
    <h1>TCP/IP Protocol Suite</h1>

    <table>
        <tr>
            <th>Layer</th>
            <th>Protocols</th>
        </tr>
        <tr>
            <td>Application Layer</td>
            <td>
                HTTP<br>
                HTTPS<br>
                FTP<br>
                DNS<br>
                Telnet<br>
                SSH
            </td>
        </tr>
        <tr>
            <td>Transport Layer</td>
            <td>
                TCP<br>
                UDP
            </td>
        </tr>
        <tr>
            <td>Internet Layer</td>
            <td>
                IP<br>
                ICMP<br>
                IPv4<br>
                IPv6<br>
            </td>
        </tr>
        <tr>
            <td>Network Access Layer</td>
            <td>
                Ethernet<br>
                Wi-Fi (IEEE 802.11)<br><br>
            </td>
        </tr>
    </table>
</body>
</html>

'''

class MyServer(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request recevied...")
        self.sen_response(200)
        self.send_header("content-type", "text/html")
        self.end_headers()
        self.wfile.write(content.encode())

print("This is my webserver")
server_address =('',8000)
httpd = HTTPServer(server_address,MyServer)
httpd.serve_forever()
```
# OUTPUT:
![alt text](<Screenshot 2025-09-19 134148.png>)
![alt text](<Screenshot 2025-09-19 134315.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.

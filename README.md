# EX01 Developing a Simple Webserver

# Date:08-10-2024
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

~~~

from importlib.resources import contents
from django.shortcuts import render

from http.server import BaseHTTPRequestHandler, HTTPServer

content='''
<html>
<head>
    <style>
        body {
            font-family: Arial, sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f9f9f9;
            display: flex;
            justify-content: center;
            align-items: center;
            height: 100vh;
        }

        .specs-table {
            border-collapse: collapse;
            width: 60%;
            margin: 20px auto;
            background-color: #ffffff;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
        }

        .specs-table thead th {
            background-color: #4CAF50;
            color: white;
            font-size: 1.5em;
            text-align: center;
            padding: 15px;
        }

        .specs-table tbody tr {
            border-bottom: 1px solid #ddd;
        }

        .specs-table tbody tr:nth-child(even) {
            background-color: #f2f2f2;
        }

        .specs-table tbody tr:hover {
            background-color: #f1f1f1;
        }

        .specs-table td, .specs-table th {
            padding: 12px;
            text-align: left;
        }

        .specs-table td {
            color: #333;
            font-size: 1em;
        }
    </style>
</head>
<body>

    <table class="specs-table">
        <thead>
            <tr>
                <th colspan="2" style="text-align: center;">Laptop Specs</th>
            </tr>
        </thead>
        <tbody>
            <tr>
                <td>Device name</td>
                <td>NAVEEN's PC</td>
            </tr>
            <tr>
                <td>Processor</td>
                <td>13th Gen Intel(R) Core(TM) i5-1335U   1.30 GHz</td>
            </tr>
            <tr>
                <td>Installed RAM</td>
                <td>16.0 GB (15.7 GB usable)</td>
            </tr>
            <tr>
                <td>System type</td>
                <td>64-bit operating system, x64-based processor</td>
            </tr>
            <tr>
                <td>Pen and touch</td>
                <td>No pen or touch input is available for this display</td>
            </tr>
        </tbody>
    </table>

</body>
</html>

'''




class myserver(BaseHTTPRequestHandler):
    def do_GET(self):
        print("Get request received....")
        self.send_response(200)
        self.send_header("content-type","text/html")
        self.end_headers()
        self.wfile.write(content.encode()) 
print("This is my webserver!")
server_address = ('',8000)
httpd=HTTPServer(server_address,myserver)
httpd.serve_forever()
~~~
# OUTPUT:

![Screenshot 2024-12-06 103939](https://github.com/user-attachments/assets/aee15c98-76fc-4fb5-91eb-aa63a337729a)
![Screenshot 2024-12-06 104113](https://github.com/user-attachments/assets/621fec04-3a8a-4912-a28d-f7fe41fa30f9)


# RESULT:
The program for implementing simple webserver is executed successfully.

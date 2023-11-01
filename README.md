# EX01 Developing a Simple Webserver
## Date:

## AIM:
To develop a simple webserver to serve html pages.

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
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<html>
       <title> coding </title>
       <body>
            <table border ="2">
                <caption> Top five Revenue software companies </caption>
                 <tr>

                          <th>S.No</th>
                          <td> 1 </td>
                          <td> 2 </td>
                          <td> 3 </td>
                          <td> 4 </td>
                          <td> 5 </td>
                          
                     
                 </tr>
                 <tr>
                       <th> company </th>
                       <td> flipkart </td>
                       <td> Oracel </td>
                       <td> Amason </td>
                       <td> IBM </td>
                       <td> toodle </td>
                </tr>
                <tr>
                       <th> Revenue </th>
                       <td> 6 billion </td>
                       <td> 9 billion </td>
                       <td> 10 billion </td>
                       <td> 15 billion </td>
                       <td> 20 billion </td>
         
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
![Output](<out1.png>)

![Output](<out2.png>)

## RESULT:
The program for implementing simple webserver is executed successfully.

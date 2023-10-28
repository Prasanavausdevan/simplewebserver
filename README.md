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
<html>
	<title>web page </title>
<body>
	<table border="3" cellspacing="10">
	<caption> Top five Revenue Generating Software Companies </caption>
	<tr>
		<th> S.NO </th>
		<th>Company </th>
		<th> Revenue </th>
	</tr>
	<tr>
	<td> 1 </td>
	<td> MICROSOFT </td>
	<td> 65 Billion </td>
	</tr>
	<tr>
	<td> 2 </td>
	<td> Oracle </td>
	<td> 29.6 billion </td>
	</tr>
	<tr>
	<td> 3 </td>
	<td> IBM </td>
	<td> 29.1 billion </td>
	</tr>
	<tr>
	<td> 4 </td>
	<td> SAP </td>
	<td> 6.4 billion </td>
	</tr>
	<tr>
	<td> 5 </td>
	<td> Symantec </td>
	<td> 5.6 billion </td>
	</tr>
	</table>
</body>
</html>
 
```
```
from http.server import HTTPServer, BaseHTTPRequestHandler
content = """
<!DOCTYPE html>
<html>
<head>
<title>My webserver</title>
</head>
<body>
<h1>Welcome<h1>
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

![Alt text](<Screenshot 2023-10-25 093334.png>)
## RESULT:
The program for implementing simple webserver is executed successfully.

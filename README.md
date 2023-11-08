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
![Screenshot 2023-11-08 085210](https://github.com/Prasanavausdevan/simplewebserver/assets/144870579/82d06baf-654b-414c-a315-443edaf9320b)
![z](https://github.com/Prasanavausdevan/simplewebserver/assets/144870579/5cc76de5-8263-49b4-9a64-f946ba46ba5a)




## RESULT:
The program for implementing simple webserver is executed successfully.

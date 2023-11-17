# EX01 Developing a Simple Webserver
## Date: 7.10.2023

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
<!DOCTYPE html>
<html>
   <title>revenue of top software companies</title>
       <body bgcolor="cyan">
          <table border="6" cellspacing="4" cellpadding="4">
              <caption>Top Five Revenue Generating Software Company   [from lowest to highest ]</caption>
                  <tr>
                    <th>S.no</th>
                    <th>Company</th>
                    <th>Revenue</th>
                 </tr>

                 <tr>
                   <th>1</th>
                   <td>Symantec</td>
                   <td>5.6 billion</td>
                </tr>

                 <tr>
                   <th>2</th>
                   <td>SAP</td>
                   <td>6.4 billion</td>
                </tr>

                 <tr>
                   <th>3</th>
                   <td>IBM</td>
                   <td>29.1 billion</td>
                </tr>

                 <tr>
                   <th>4</th>
                   <td>Oracle</td>
                   <td>29.6 billion</td>
                </tr>

                 <tr>
                   <th>5</th>
                   <td>Microsoft</td>
                   <td>65 billion</td>
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
![Screenshot 2023-10-25 100333](https://github.com/EPriyadharshini/simplewebserver/assets/144870831/32e94959-63c2-4d98-b8cc-0be146c6867e)
![Screenshot 2023-10-25 100417](https://github.com/EPriyadharshini/simplewebserver/assets/144870831/59c666b2-36c6-4d2b-a757-a1fc354ff102)


## RESULT:
The program for implementing simple webserver is executed successfully.

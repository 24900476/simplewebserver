# EX01 Developing a Simple Webserver
## Date:26.10.2024

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
from http.server import HTTPServer,BaseHTTPRequestHandler

content='''
<html>
    <body>
      <title>MY SERVER </title>
     <table border="5" bgcolor="violet" cellpadding="10"> 
    <caption align="center"></caption>
    <th colspan="7" align="center" bgcolor="purple">LAPTOP CONFIGURATION
    </th>
     <tr>
        <th>S.NO</th>
        <th>SPECIFICATIONS</th>
        <th>DETAILS</th>

     </tr>
     <tr> 
        <td> 1</td>
        <td> Device Name</td>
        <td> LAPTOP-DDDV9M3B</td>
        
     </tr>
     <tr>
        <td> 2</td> 
        <td>PROCESSOR</td>
        <td>11th Gen intel(R) Core(TM) i3-1115G4 @ 3.00GHz 2.90gGHz</td>
        
     </tr>
     <tr>
        <td> 3 </td>
        <td>Installed RAM</td>
        <td>8.00 GB (7.65 GB usable)</td>
      
     </tr>
     <tr>
      <td> 4 </td>
      <td>Device ID</td>
      <td>59DF6D12-AFDC-4C90-AOAB-5E33B8A2637A</td>
    
   </tr>
   <tr>
      <td> 5</td>
      <td>Product ID</td>
      <td>00356-24701-66895-AAOEM</td>
    
   </tr>
   <tr>
      <td> 6 </td>
      <td>System type </td>
      <td>64-bit operating system,x64-based processor</td>
    
   </tr>
   <tr>
      <td> 7 </td>
      <td>Pen and touch</td>
      <td>No pen or touch input is available for this display</td>
    
   </tr>
     </table>
    </body>
</html>'''  

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

## OUTPUT:
![alt text](<Screenshot (3).png>)
![alt text](<Screenshot 2024-10-26 133220.png>)





## RESULT:
The program for implementing simple webserver is executed successfully.

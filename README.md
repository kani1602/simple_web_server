# EX01 Developing a Simple Webserver

# Date:  18-10-2024
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
    from http.server import HTTPServer, BaseHTTPRequestHandler
    content = """
    <!DOCTYPE html>
    <html lang="en">
    <head>
        <meta charset="UTF-8">
        <meta name="viewport" content="width=device-width, initial-scale=1.0">
        <title>laptop configuration</title>
    </head>
    <style>
        body{
            background-color:rgb(255, 255, 255);
        }

        table{
            background-color:rgb(25, 119, 213);
            border-collapse: collapse;
            box-shadow: 0;
            margin: 60px;
            text-align: center;
            color: black;
        }
        header{
            font-size: 420%;
            background-color: rgb(154, 162, 155);
        }

    </style>
    <body>
        <center>
            <header>
                MY LAPTOP CONFIGURATION
            </header>
        <table border="4px" width="600" height="400">
            <div class="heading">
            <tr style="font-size: x-large;">
                <th>S.NO</th>
                <th>COMPONENTS</th>
                <th>DETAILS</th>
            </tr>
            </div>
            <tr>
                <th>1</th>
                <th style="font-style: inherit;">PROCESSOR(CPU)</th>
                <td>AMD Ryzen 9 7900x </td>
            </tr>
            <tr>
                <th>2</th>
                <th style="font-style: inherit;">MEMORY(RAM)</th>
                <td>32.0 GB</td>
            </tr>
            <tr>
                <th>3</th>
                <th style="font-style: inherit;">STORAGE</th>
                <td>1TB SSD</td>
            </tr>
            <tr>
                <th>4</th>
                <th style="font-style: inherit;">DISPLAY</th>
                <td>15.6-inch Full HD (1920x1080)</td>
            </tr>
            <tr>
                <th>5</th>
                <th style="font-style: inherit;">GRAPHICS(GPU)</th>
                <td>Integrated Intel UHD</td>
            </tr>
            <tr>
                <th>6</th>
                <th style="font-style: inherit;">BATTERY</th>
                <td>110 Wh, Up to 12 hours</td>
            </tr>
            <tr>
                <th>7</th>
                <th style="font-style: inherit;">OPERATING SYSTEM</th>
                <td>Windows 11 Pro</td>
            </tr>

        </table>
        </center>
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

# OUTPUT:
![alt text](<Screenshot (50).png>) 

![alt text](<Screenshot 2024-12-07 232039.png>)

# RESULT:
The program for implementing simple webserver is executed successfully.

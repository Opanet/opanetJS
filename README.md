# opanetJS
OpanetJS encapsulate Opanet Identity &amp; Core Payment features into a simple to use Javascript library for web developers to improve user experience in accessing digital payments, collection services and granting secure access to user resources across applications.

## Usage  
TEST  

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <script type="text/javascript" src="https://dwete.com:9090/developer/Scripts/jquery-1.9.1.js"></script>
      <script type="text/javascript" src="https://dwete.com:9090/developer/Scripts/jquery.signalR-2.2.2.min.js"></script>
      <script type="text/javascript" src="https://dwete.com:9090/developer/signalr/hubs"></script>
      <script type="text/javascript" src="https://dwete.com:9090/developer/Scripts/opanet.js"></script>
    </head>
    <body>
      <script type="text/javascript">
        opanet.ready(function () {});
      </script>
    </body>
    </html>

LIVE 

    <!DOCTYPE html>
    <html lang="en">
    <head>
      <script type="text/javascript" src="https://dwete.com/developer/Scripts/jquery-1.9.1.js"></script>
      <script type="text/javascript" src="https://dwete.com/developer/Scripts/jquery.signalR-2.2.2.min.js"></script>
      <script type="text/javascript" src="https://dwete.com/developer/signalr/hubs"></script>
      <script type="text/javascript" src="https://dwete.com/developer/Scripts/opanet.js"></script>
    </head>
    <body>
      <script type="text/javascript">
        opanet.ready(function () {});
      </script>
    </body>
    </html>  

## .ready(handler) 
Description: Specify a function to execute when Opanet is fully loaded.  

**Handler** 
Type: Function()  
A function to execute when Opanet is fully loaded.  

    opanet.ready(function(){
     //handler for .ready() called.
    });

Read More: [Opanet Wiki](https://github.com/Opanet/opanetJS/wiki)  
Website: [Opanet.org](https://opanet.org)  
Contact: opoku.paul@opanet.org

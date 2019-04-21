# The OPEN wallet, identity & access platform for internet business.  
**Opanet** is a technology platform for building payments, collections and security into applications. It is the quickest way to go from idea to app.  
### FEATURES
* Opanet allows you to setup e-wallets enabling you to manage collections, transfers and splitting of funds between users.    
* Make payments easy for your users by allowing them to pay with various payment methods (Visa, Master Card, Mobile Money, Dwete, E-switch, E-check). Accept payment on your website or app with our checkout form or Build any type of payment flow including recurring billing, split payment and many more with our APIs.  
* Build Two Factor Authentication into your app.  
* Opanet Single-sign-on (SSO) enables a user to log in with a single ID and password to gain access to several apps across your enterprise. Opanet Single-sign-on is also your gateway to connecting with Opanet's users and services in a secure manner.  

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

Read More: [opanetJS Wiki](https://github.com/Opanet/opanetJS/wiki)  
Website: [Opanet.org](https://opanet.org)  
Contact: opoku.paul@opanet.org

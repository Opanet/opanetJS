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

## .login(appId, appToken,permissions,successHandler,failureHandler)  
Description: Present a secure login page to authenticate app users. Add a layer of protection by enabling two factor authentication and Single-sign-on.  
 ![Opanet, Login](https://dwete.com/developer/assets/img/2FA/login_large.png) 
 ![Opanet, Login](https://dwete.com/developer/assets/img/2FA/login_large_confirmMobile.png) 
**appId**  
Type: string  
The unique id assigned to your app by Opanet.  
Login to your [Opanet Account](https://opanet.org/console/opanetLogin.html) to create an App.  

**appToken**  
Type: string  
A token for authenticating an app.  
Follow this [guide](https://api.opanet.org/#3584437d-de31-4be9-a913-27cf47b65395) to generate an appToken.  

**permissions**  
Type: Array  
Features of Opanet you want users to access in your app.  
Most functions/features on Opanet requires user to grant your app permission before execution.  
![Opanet, Login](https://dwete.com/developer/assets/img/2FA/permission_large.png) 
 
**successHandler**  
Type: Function(response)  
A function to execute when login is successful.  

**failureHandler**
Type: Function(response)  
A function to execute when login fails.   

    var appToken = "xmu9fzsfo3Q22bCHNBumMyY90i9OtdQBK+Ew8dqVof/GzyRs4QwinRW09jNXWqLxwT92YCvcerpp5rfR2TPr5zUAW57fuqkIikJ1t+qFR3NNqBX39IwqZ6LmetY5erVBFY7RrPsdxvT5ObAyUPcBLw==";  
        var appId = "git1234";
        Var permissions = [
                        "opanet_identity_post_profile",
                        "opanet_identity_get_myGroups",
                        "opanet_identity_get_accounts",
                        "opanet_identity_get_profile",
                        "opanet_identity_get_customData",
                        "opanet_identity_post_joinGroup",
                        "opanet_identity_post_leaveGroup",
                        "opanet_identity_post_profileImage",
                        "opanet_identity_post_coverPhoto",
                        "opanet_identity_post_customData",
                        "opanet_identity_post_defaultAccount",
                        "opanet_identity_delete_customData",
                        "opanet_identity_get_accounts",
                        "opanet_wallet_get_balance",
                        "opanet_wallet_get_transactionLookup",
                        "opanet_billing_get_detail",
                        "opanet_billing_post_cancel",
                        "opanet_billing_post_billLookup",
                        "opanet_billing_post_createInvoice",
                        "opanet_checkout_post_createInvoice"
                    ];
        opanet.login(appId, appToken, permissions,
            (response) => { console.log(response.accessToken)},
            (response) => { console.log(response.message)} 
            );  




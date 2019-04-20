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

## .logout(successHandler,failureHandler)  
Description: Logout a user from your app.

**successHandler**  
Type: Function(response)  
A function to execute when user successfully logout.  

**failureHandler**  
Type: Function(response)  
A function to execute when logout fails.  

    opanet.logout(
    x=>{console.log(x.message)},
    x=>{console.log(x.message)}
    );  


## .identity.getProfile(successHandler,failureHandler)  
Description: Get the profile/kyc of a user.  
Permission: __opanet_identity_get_profile__  

**successHandler**  
Type: Function(response)
A function to execute when Opanet returns a user profile to your app.

**failureHandler**  
Type: Function(response)    
A function to execute when getProfile fails.    

    opanet.identity.getProfile(
    x=>{console.log(x.firstName)},
    x=>{console.log(x.message)}
    );  

## .identity.updateProfile(personalProfile,successHandler,failureHandler)  
Description: Update a user profile/kyc.  
Permission: __opanet_identity_post_profile__  

**personalProfile**   
Type: Object  
The user profile/kyc.  

**successHandler**  
Type: Function()  
A function to execute when updateProfile is successful.  

**failureHandler**  
Type: Function()  
A function to execute when updateProfile fails.  

The profile object can take any of the value pair. Only provide the value pair you want to update.  

        Var profile = {
            firstName: "Paul",
            lastName: "Opoku",
            otherNames: " ",
            occupation: "Software Engineer",
            gender: "male",
            dateOfBirth: "1954-02-01",
            email: "opoku.paul@smartgeni.com",
            mobile: "233548070810",
            nationality: "Ghana",
            contact: {
                id: "AA19540201967",
                officeTelephone: "0322123456",
                homeTelephone: "",
                mobile1: "0244123456",
                mobile2: "",
                zipCode: "",
                email: "secondarymail@domain.com",
                website: null
            },
            location: {
                id: "AA19540201967",
                street: "kwamo Highway",
                city: "Kumasi",
                region: "Ashanti",
                country: "Ghana"
            }
        }

        opanet.identity.updateProfile(
            profile,
            x => { console.log(x.firstName) },
            x => { console.log(x.message) }
        );
        

## .identity.updatePhoto(image,successHandler,failureHandler)  
Description: Update a user profile photo.  
Permission: __opanet_identity_post_profileImage__  

**image**  
Type: string  
Image as Base64string.  

**successHandler**  
Type: Function()  
A function to execute when updatePhoto is successful.  

**failureHandler**
Type: Function()  
A function to execute when updatePhoto fails.  


## .billing.checkout(appId, token, isAppToken, invoice, successHandler, failureHandler)  
Description: Present a secure web terminal to accept payment.  
Permission: __opanet_billing_post_createInvoice__   
![Opanet, Checkout](https://dwete.com/developer/assets/img/2FA/checkout_large.png) 

**appId**
Type: string  
The unique id assigned to your app by Opanet.  

**token**  
Type: string  
An appToken or userToken(accessToken) for authentication.  

**isAppToken**  
Type: boolean  
True if token is an appToken; False if token is a userToken.  

**invoice**
Type: Object  
The sales invoice to be paid.   

**successHandler**  
Type: Function()  
A function to execute when payment is successful.  

**failureHandler**  
Type: Function()  
A function to execute when payment fails.  

    var token = "xmu9fzsfo3Q22bCHNBumMyY90i9OtdQBK+Ew8dqVof/GzyRs4QwinRW09jNXWqLxwT92YCvcerpp5rfR2TPr5zUAW57fuqkIikJ1t+qFR3NNqBX39IwqZ6LmetY5erVBFY7RrPsdxvT5ObAyUPcBLw==";
    var appId = "git1234";
    var invoice = {
            merchantId: "yo082507",
            amount: 1.00,
            customerName: "Opoku Paul",
            description: "Membership",
            customerMobile: "233548079999",
            dueDate: "2018/08/01",
            tax: 0.00,           
            items: [{ 
                      "description": "Registration", 
                      "quantity": 1, 
                      "unitPrice": 1.00 
                    }]
              }      
    opanet.billing.checkout(appId,token, true, invoice,
                        x => { console.log(x) },
                        x => { console.log(x) });
       




## .billing.widthdraw(appId, token, isAppToken, payload, successHandler, failureHandler)  
Description: Present a secure web terminal to transfer fund from your personal wallet (Opanet Credit) to mobile money or bank account.  
Permission: __opanet_billing_post_withdraw__  
![Opanet, Withdrawal](https://dwete.com/developer/assets/img/2FA/withdraw_large_bk.png) 

**appId**  
Type: string  
The unique id assigned to your app by Opanet.  

**token**  
Type: string  
An appToken or userToken(accessToken) for authentication.  

**isAppToken**  
Type: boolean  
True if token is an appToken; False if token is a userToken.  

**payload**  
Type: Object  
Amount, Narration & Expiry (Session duration of the terminal).   

**successHandler**  
Type: Function()  
A function to execute when payment is successful.  

**failureHandler**
Type: Function()  
A function to execute when payment fails.  

    var token = "xmu9fzsfo3Q22bCHNBumMyY90i9OtdQBK+Ew8dqVof/GzyRs4QwinRW09jNXWqLxwT92YCvcerpp5rfR2TPr5zUAW57fuqkIikJ1t+qFR3NNqBX39IwqZ6LmetY5erVBFY7RrPsdxvT5ObAyUPcBLw==";
    var appId = "git1234";
    var payload = {
                    "amount":1,
                    "narration":"Live test",
                    "expiry":60
                   }      
    opanet.billing.checkout(appId,token, true, payload,
                        x => { console.log(x) },
                        x => { console.log(x) });
                        
## .wallet.personal.balance(successHandler,failureHandler)  
Description: Get personal wallet balance.  
Permission: __opanet_wallet_get_balance__    

**successHandler**  
Type: Function()  
A function to execute when successful.  

**failureHandler**
Type: Function()  
A function to execute when fails.

## .wallet.personal.transactionLookup(page, startDate, endDate, successHandler, failureHandler)  
Description: Get personal wallet transaction history.  
Permission: __opanet_wallet_get_transactionLookup__    

**page**  
Type: integer  
Page number, the first page being 1 (A page returns 100 records).  

**startDate**  
Type: Date  
Start Date.

**startDate**  
Type: Date  
End Date.  

**successHandler**  
Type: Function()  
A function to execute when successful.  

**failureHandler**
Type: Function()  
A function to execute when fails.

## .wallet.group.balance(groupId,successHandler,failureHandler)  
Description: Get group wallet balance.  
Permission: __opanet_corporate_get_balance__    

**groupId**  
Type: string  
The account Id of the group.

**successHandler**  
Type: Function()  
A function to execute when successful.  

**failureHandler**
Type: Function()  
A function to execute when fails.

## .wallet.group.transactionLookup(groupId, page, startDate, endDate, successHandler, failureHandler)  
Description: Get group wallet transaction history.  
Permission: __opanet_corporate_get_transactionLookup__    

**groupId**  
Type: string  
The account Id of the group.

**page**  
Type: integer  
Page number, the first page being 1 (A page returns 100 records).  

**startDate**  
Type: Date  
Start Date.

**startDate**  
Type: Date  
End Date.  

**successHandler**  
Type: Function()  
A function to execute when successful.  

**failureHandler**
Type: Function()  
A function to execute when fails.






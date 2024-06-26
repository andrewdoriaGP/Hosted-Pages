# Hosted Wallet Page

The PayFabric hosted wallet page is used for embedding the wallet page into your application to allow your users to create or update their credit card / eCheck details (including billing address information).

## Generate Security Token

There are two hosted wallet page, create and edit. Before embedding the desired wallet page, please ensure the following:

- Create a Credit Card / eCheck
  
  - Generate a [Security Token](/Sections/Security%20Token.md).  Assume the token value is @TOKEN. 
  - Build the hosted create wallet page URL this way:

    https://sandbox.payfabric.com/Payment/Web/Wallet/Create?customer={CUSTOMER_NUMBER}&tender={TENDER}&token={@TOKEN}  

    {CUSTOMER_NUMBER} = Your customers unique identifier  
    {TENDER} = *CreditCard* or *ECheck*

- Edit a Credit Card / eCheck

  -  Generate a [Security Token](/Sections/Security%20Token.md).  Assume the token value is @TOKEN. 
  -  Retrieve the unique card Id, see our [API documentation](../../../../PayFabric-APIs/blob/master/PayFabric/Sections/Wallets.md#retrieve-credit-cards--echecks) for how.  Assume the card Id is @CARDID.
  -  Build the hosted edit wallet page URL this way:
  
     https://sandbox.payfabric.com/Payment/Web/Wallet/edit?card={@CARDID}&token={@TOKEN}


## Optional Parameters

PayFabric hosted wallet page accepts the query string parameters below. Separate each parameter with ampersand ('&') to for the query string and add the query string to the hosted wallet page URL.

>
| QueryString| Description | 
| :------------- | :------------- | 
|Country=&Street1=&Street2=&Street3=<br/>&City=&State=&Zip=&Email=&Phone= |This query string can pass initial billing address information|
|ThemeName|This parameter is to support 3rd party dynamically passing into the theme name via query string. If the value is an existing theme name, then page will use this theme; If the value is a nonexistent theme name, then the page will use the device default theme.|
|ReturnURI|When a valid URL is provided in ReturnURI, after the wallet record is saved, the hosted wallet page will redirect the user to the URL specified with the unique Wallet ID appended to the URL.  Note: This parameter is only supported with the create wallet operation.|
|isusenewtheme|	When the value is `1`, PayFabric's hosted page URL will trigger the V3 layout instead of the V2 Layout. The default value is `0`. **Note:** This query string only works for the non-responsive hosted create/edit wallet pages.|
|UseBluefin|This parameter will take affect when [BlueFin Profile](https://github.com/PayFabric/Portal/blob/master/PayFabric/Sections/Bluefin.md) get enabled. When the value is '0', only regular keyboard entry for the credit card is available, when the value is `1`, only encryption key entry via Bluefin device for the credit card is available, when the value is `2`, both regular keyboard & encryption key entry for the credit card is available.|
|TrxInitiation|	This parameter specifies the wallet creation/updating initiated by the Merchant or Customer.|


## Wallet Pages

** Overview Intro

** Insert Link
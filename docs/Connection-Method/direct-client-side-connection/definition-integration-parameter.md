# Definition of Parameters in the Integration Page 

The following are the parameters for integration. PayDollar PayGate is case sensitive. Make sure the
typeface is correct. When a transaction is finished, the system will return customer a payment message.
Merchant can create static HTML pages to display the message. If merchant’s web site supports data
feed, the system can return payment message as shown in the following table

| Parameters  | Data Type | Descriptions |
| -------- | ------- | ------- |
| orderRef | Text (35)  | Merchant‘s Order Reference Number |
| currCode | Text (3)  | The currency of the payment: <br></br>  &nbsp;“344” – HKD<br></br>“840” – USD “702” – SGD |
| amount | Number (12,2)  | The total amount you want to charge the customer for the provided currency.<br></br>Remark:<br></br>mpsMode = SCP, the amount should be calculated in foreign currency.<br></br>mpsMode = MCP, the amount should be calculated in base currency. |
| orderRef | Text (35)  | Merchant‘s Order Reference Number |

### Parameters for Supporting 3DS 2.0 

| Parameters  | Data Type | Descriptions |
| -------- | ------- | ------- |
| orderRef | Text (35)  | Merchant‘s Order Reference Number |
| currCode | Text (3)  | The currency of the payment: <br></br>  &nbsp;“344” – HKD<br></br>“840” – USD “702” – SGD |
| amount | Number (12,2)  | The total amount you want to charge the customer for the provided currency.<br></br>Remark:<br></br>mpsMode = SCP, the amount should be calculated in foreign currency.<br></br>mpsMode = MCP, the amount should be calculated in base currency. |
| orderRef | Text (35)  | Merchant‘s Order Reference Number |

#### Example of Client Post Method (Source Code) 

The following is an example of integration of shopping cart routine with the payment routine of PayDollar
PayGate in HTML. It is noteworthy that the portion in bold typeface as follows is mandatory for
successful integration. 

In the following sample form, hidden fields are used to hold the values: 

``` 
<form name="payFormCcard" method="post" action="
https://test.paydollar.com/b2cDemo/eng/payment/payForm.jsp">
<input type="hidden" name="merchantId" value="1">
<input type="hidden" name="amount" value="3000" >
<input type="hidden" name="orderRef" value="000000000014">
<input type="hidden" name="currCode" value="344" >
<input type="hidden" name="mpsMode" value="NIL" >
<input type="hidden" name="successUrl"
value="http://www.yourdomain.com/Success.html">
<input type="hidden" name="failUrl" value="http://www.yourdomain.com/Fail.html">
<input type="hidden" name="cancelUrl"
value="http://www.yourdomain.com/Cancel.html">
<input type="hidden" name="payType" value="N"> 
<input type="hidden" name="lang" value="E">
<input type="hidden" name="payMethod" value="CC">
<input type="hidden" name="secureHash"
value="44f3760c201d3688440f62497736bfa2aadd1bc0">
<input type="submit" name="submit">
</form>
```

### Kick Off 

After the integration has been completed, it is ready to launch your e-commerce web to serve your
customers. Please copy the following TESTING URL for client post method: 

``` 
https://test.paydollar.com/b2cDemo/eng/payment/payForm.jsp
```

Please copy the following **PRODUCTION URL** for client post method: 

```
https://www.paydollar.com/b2c2/eng/payment/payForm.jsp
```
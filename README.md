# Paypal Website Payments Pro Component for CakePHP 2.2.X

### Requirements

* CakePHP 2.2.X
* A PayPal Website Payments Pro account
* A API username, password and signature (From PayPal -> Profile -> API Settings -> Signature)
* A valid SSL certificate

### Installation

1. Update the component with your API username and signature
2. Ensure component is configured with `$sandboxMode = true`
3. In your browser, log in to PayPal sandbox
3. In another browser tab, go to the PaymentsController's index action at `/payments`

This component can handle two types of PayPal transaction, Express Checkout and Direct Payment.

## Express Checkout

https://cms.paypal.com/us/cgi-bin/?cmd=_render-content&content_ID=developer/e_howto_api_WPGettingStarted

First, set some basic information about the transaction you want to perform, amount, currency etc. and call `Paypal::expressCheckout()`. 

The user is redirected to PayPal where they log in, they are then redirected back to your site (to the return URL).

You can then use `Paypal::getExpressCheckoutDetails()` to fetch basic customer information, their billing address etc.

If they are happy and want to proceed with the purchase, call `Paypal::doExpressCheckoutPayment()` which then completes the payment.

## Direct Payment

https://cms.paypal.com/us/cgi-bin/?cmd=_render-content&content_ID=developer/e_howto_api_WPDirectPayment

The customer enters their billing information on your website (SSL required) and you use this to call `Paypal::doDirectPayment()` which will attempt to bill their card.

### Notes

<strong>Do not store any credit card data, numbers, dates, CVV numbers etc. in your database, sessions, cookies.</strong>

Ensure you understand the legal requirements regarding PCI compliance when handling card data.

Enjoy!



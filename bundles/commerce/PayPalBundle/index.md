<a id="bundle-docs-commerce-paypal-bundle"></a>

# OroPayPalBundle

<a href="https://github.com/oroinc/orocommerce/tree/master/src/Oro/Bundle/PayPalBundle" target="_blank">OroPayPalBundle</a> adds <a href="https://www.paypal.com/" target="_blank">PayPal</a> integration to the OroCommerce application. For the OroCommerce back-office administrator, the bundle provides the ability to enable and configure PayPal payment methods for customer orders. Once PayPal payment methods are enabled, customer users can pay for orders using their existing PayPal account or credit and debit cards.

## Testing PayPal Response

The process of purchasing through PayPal Payments Pro or Payflow Gateway includes listening to a notify response from PayPal servers. To make payments more secure, we have implemented the IP address filtering which only accepts responses from the PayPal server addresses\` white list. The white list itself is stored in the *PayflowIPCheckListener* class by default.

For this IP check to work, the bundle has to be able to resolve the IP address from the request that is coming from a PayPal server. This is usually the case in the production environment when you have your server exposed to the internet.

To test the payments on the developer machine, you can use some kind of tunneling service, for example <a href="https://ngrok.com" target="_blank">Ngrok</a>. However, there can be some issues with the tunneling services. They tend to put the original request IP address in the header (e.g., X-Forwarded-For), and Symfony doesn’t resolve this address as client IP by default.

Luckily, there is a way for Symfony to do that by enabling trusted proxies. For the detailed explanation, refer to <a href="https://symfony.com/doc/6.4/deployment/proxies.html" target="_blank">How to Configure Symfony to Work behind a Load Balancer or a Reverse Proxy</a>.

## IP Address Whitelist Settings

To change whitelist of IP addresses, define it in the `oro_paypal` section with the `allowed_ips` property:

```yaml
oro_paypal:
   allowed_ips:
      - 255.255.255.1
      - 255.255.255.2
      - 255.255.255.3
      - 255.255.254.0/24
      - 2001:db8::85a3:0:8a2e:370:7334,
      - 2001:db8::85a3:0:8a2e:370:7334/64
```

<!-- Frontend -->

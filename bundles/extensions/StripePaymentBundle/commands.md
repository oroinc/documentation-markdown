<a id="bundle-docs-extensions-stripe-payment-bundle-commands"></a>

# CLI Commands (OroStripePaymentBundle)

## oro:cron:stripe-payment:re-authorize

The `oro:cron:stripe-payment:re-authorize` initiates renewal of payment authorization for uncaptured payments that are about to expire.

Uncaptured payments automatically expire a set number of days after creation (7 days by default).
Once expired, they are marked as refunded, and any attempt to capture them will fail.

The command is run automatically by the cron job every hour, but you can also run it manually:

```none
php bin/console oro:cron:stripe-payment:re-authorize
```

<!-- Frontend -->

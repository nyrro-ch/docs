# Config Settings

In addition to the settings in **Commerce** → **Settings**, the config items below can be saved in a `config/commerce.php` file using the same format as [Craft’s general config settings](/4.x/config/config-settings.md).

For example, if you wanted to change the [inactive carts duration](#purgeinactivecartsduration) in dev environments but not on staging or production, you could do this:

```php{9}
return [
    // Global settings
    '*' => [
        // ...
    ],

    // Dev environment settings
    'dev' => [
        'purgeInactiveCartsDuration' => 'P1D',
        // ...
    ],

    // Staging environment settings
    'staging' => [
        // ...
    ],

    // Production environment settings
    'production' => [
        // ...
    ],
];
```

You can access the Commerce [general settings model](commerce4:craft\commerce\models\Settings) in your templates:

```twig
{% set settings = craft.commerce.settings %}
```

Here’s the full list of Commerce config settings:

<!-- BEGIN SETTINGS -->

## System

### `defaultView`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'commerce/orders'`

Defined by
:  [Settings::$defaultView](commerce4:craft\commerce\models\Settings::$defaultView)

Since
:  2.2

</div>

Commerce’s default control panel view. (Defaults to order index.)



### `emailSenderAddress`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string), [null](https://php.net/language.types.null)

Default value
:  `null`

Defined by
:  [Settings::$emailSenderAddress](commerce4:craft\commerce\models\Settings::$emailSenderAddress)

</div>

Default email address Commerce system messages should be sent from.

If `null` (default), Craft’s [MailSettings::$fromEmail](craft4:craft\models\MailSettings::$fromEmail) will be used.



### `emailSenderAddressPlaceholder`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string), [null](https://php.net/language.types.null)

Default value
:  `null`

Defined by
:  [Settings::$emailSenderAddressPlaceholder](commerce4:craft\commerce\models\Settings::$emailSenderAddressPlaceholder)

</div>

Placeholder value displayed for the sender address control panel settings field.

If `null` (default), Craft’s [MailSettings::$fromEmail](craft4:craft\models\MailSettings::$fromEmail) will be used.



### `emailSenderName`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string), [null](https://php.net/language.types.null)

Default value
:  `null`

Defined by
:  [Settings::$emailSenderName](commerce4:craft\commerce\models\Settings::$emailSenderName)

</div>

Default from name used for Commerce system emails.

If `null` (default), Craft’s [MailSettings::$fromName](craft4:craft\models\MailSettings::$fromName) will be used.



### `emailSenderNamePlaceholder`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string), [null](https://php.net/language.types.null)

Default value
:  `null`

Defined by
:  [Settings::$emailSenderNamePlaceholder](commerce4:craft\commerce\models\Settings::$emailSenderNamePlaceholder)

</div>

Placeholder value displayed for the sender name control panel settings field.

If `null` (default), Craft’s [MailSettings::$fromName](craft4:craft\models\MailSettings::$fromName) will be used.



### `showEditUserCommerceTab`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `true`

Defined by
:  [Settings::$showEditUserCommerceTab](commerce4:craft\commerce\models\Settings::$showEditUserCommerceTab)

Since
:  4.0

</div>

Whether the [Commerce Tab](customers.md#user-customer-info-tab) should be shown when viewing users in the control panel.



## Cart

### `activeCartDuration`

<div class="compact">

Allowed types
:  `mixed`

Default value
:  `3600` (1 hour)

Defined by
:  [Settings::$activeCartDuration](commerce4:craft\commerce\models\Settings::$activeCartDuration)

Since
:  2.2

</div>

How long a cart should go without being updated before it’s considered inactive.

See [craft\helpers\ConfigHelper::durationInSeconds()](craft4:craft\helpers\ConfigHelper::durationInSeconds()) for a list of supported value types.



### `allowCheckoutWithoutPayment`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$allowCheckoutWithoutPayment](commerce4:craft\commerce\models\Settings::$allowCheckoutWithoutPayment)

Since
:  3.3

</div>

Whether carts are can be marked as completed without a payment.



### `allowEmptyCartOnCheckout`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$allowEmptyCartOnCheckout](commerce4:craft\commerce\models\Settings::$allowEmptyCartOnCheckout)

Since
:  2.2

</div>

Whether carts are allowed to be empty on checkout.



### `autoSetCartShippingMethodOption`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$autoSetCartShippingMethodOption](commerce4:craft\commerce\models\Settings::$autoSetCartShippingMethodOption)

</div>

Whether the first available shipping method option should be set automatically on carts.



### `autoSetNewCartAddresses`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `true`

Defined by
:  [Settings::$autoSetNewCartAddresses](commerce4:craft\commerce\models\Settings::$autoSetNewCartAddresses)

</div>

Whether the user’s primary shipping and billing addresses should be set automatically on new carts.



### `cartVariable`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'cart'`

Defined by
:  [Settings::$cartVariable](commerce4:craft\commerce\models\Settings::$cartVariable)

</div>

Key to be used when returning cart information in a response.



### `loadCartRedirectUrl`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string), [null](https://php.net/language.types.null)

Default value
:  `null`

Defined by
:  [Settings::$loadCartRedirectUrl](commerce4:craft\commerce\models\Settings::$loadCartRedirectUrl)

Since
:  3.1

</div>

Default URL to be loaded after using the [load cart controller action](orders-carts.md#loading-a-cart).

If `null` (default), Craft’s default [`siteUrl`](config4:siteUrl) will be used.



### `purgeInactiveCarts`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `true`

Defined by
:  [Settings::$purgeInactiveCarts](commerce4:craft\commerce\models\Settings::$purgeInactiveCarts)

</div>

Whether inactive carts should automatically be deleted from the database during garbage collection.

::: tip
You can control how long a cart should go without being updated before it gets deleted [`purgeInactiveCartsDuration`](#purgeinactivecartsduration) setting.
:::



### `purgeInactiveCartsDuration`

<div class="compact">

Allowed types
:  `mixed`

Default value
:  `7776000` (90 days)

Defined by
:  [Settings::$purgeInactiveCartsDuration](commerce4:craft\commerce\models\Settings::$purgeInactiveCartsDuration)

</div>

Default length of time before inactive carts are purged. (Defaults to 90 days.)

See [craft\helpers\ConfigHelper::durationInSeconds()](craft4:craft\helpers\ConfigHelper::durationInSeconds()) for a list of supported value types.



### `updateCartSearchIndexes`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `true`

Defined by
:  [Settings::$updateCartSearchIndexes](commerce4:craft\commerce\models\Settings::$updateCartSearchIndexes)

Since
:  3.1.5

</div>

Whether the search index for a cart should be updated when saving the cart via `commerce/cart/*` controller actions.

May be set to `false` to reduce performance impact on high-traffic sites.

::: warning
Setting this to `false` will result in fewer index update queue jobs, but you’ll need to manually re-index orders to ensure up-to-date cart search results in the control panel.
:::



### `validateCartCustomFieldsOnSubmission`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$validateCartCustomFieldsOnSubmission](commerce4:craft\commerce\models\Settings::$validateCartCustomFieldsOnSubmission)

Since
:  3.0.12

</div>

Whether to validate custom fields when a cart is updated.

Set to `true` to allow custom content fields to return validation errors when a cart is updated.



## Orders

### `freeOrderPaymentStrategy`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'complete'`

Defined by
:  [Settings::$freeOrderPaymentStrategy](commerce4:craft\commerce\models\Settings::$freeOrderPaymentStrategy)

</div>

How Commerce should handle free orders.

The default `'complete'` setting automatically completes zero-balance orders without forwarding them to the payment gateway.

The `'process'` setting forwards zero-balance orders to the payment gateway for processing. This can be useful if the customer’s balance
needs to be updated or otherwise adjusted by the payment gateway.



### `minimumTotalPriceStrategy`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'default'`

Defined by
:  [Settings::$minimumTotalPriceStrategy](commerce4:craft\commerce\models\Settings::$minimumTotalPriceStrategy)

</div>

How Commerce should handle minimum total price for an order.

Options:

- `'default'` [rounds](commerce4:\craft\commerce\helpers\Currency::round()) the sum of the item subtotal and adjustments.
- `'zero'` returns `0` if the result from `'default'` would’ve been negative; minimum order total is `0`.
- `'shipping'` returns the total shipping cost if the `'default'` result would’ve been negative; minimum order total equals shipping amount.



### `orderReferenceFormat`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'{{number[:7]}}'`

Defined by
:  [Settings::$orderReferenceFormat](commerce4:craft\commerce\models\Settings::$orderReferenceFormat)

</div>

Human-friendly reference number format for orders. Result must be unique.

See [Order Numbers](orders-carts.md#order-numbers).



### `pdfAllowRemoteImages`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$pdfAllowRemoteImages](commerce4:craft\commerce\models\Settings::$pdfAllowRemoteImages)

</div>

Whether to allow non-local images in generated order PDFs.



### `pdfPaperOrientation`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'portrait'`

Defined by
:  [Settings::$pdfPaperOrientation](commerce4:craft\commerce\models\Settings::$pdfPaperOrientation)

</div>

The orientation of the paper to use for generated order PDF files.

Options are `'portrait'` and `'landscape'`.



### `pdfPaperSize`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'letter'`

Defined by
:  [Settings::$pdfPaperSize](commerce4:craft\commerce\models\Settings::$pdfPaperSize)

</div>

The size of the paper to use for generated order PDFs.

The full list of supported paper sizes can be found [in the dompdf library](https://github.com/dompdf/dompdf/blob/master/src/Adapter/CPDF.php#L45).



### `requireBillingAddressAtCheckout`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$requireBillingAddressAtCheckout](commerce4:craft\commerce\models\Settings::$requireBillingAddressAtCheckout)

</div>

Whether a billing address is required before making payment on an order.



### `requireShippingAddressAtCheckout`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$requireShippingAddressAtCheckout](commerce4:craft\commerce\models\Settings::$requireShippingAddressAtCheckout)

</div>

Whether a shipping address is required before making payment on an order.



### `requireShippingMethodSelectionAtCheckout`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$requireShippingMethodSelectionAtCheckout](commerce4:craft\commerce\models\Settings::$requireShippingMethodSelectionAtCheckout)

</div>

Whether shipping method selection is required before making payment on an order.



### `updateBillingDetailsUrl`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `''`

Defined by
:  [Settings::$updateBillingDetailsUrl](commerce4:craft\commerce\models\Settings::$updateBillingDetailsUrl)

</div>

URL for a user to resolve billing issues with their subscription.

::: tip
The example templates include [a template for this page](https://github.com/craftcms/commerce/tree/main/example-templates/dist/shop/plans/update-billing-details.twig).
:::



### `useBillingAddressForTax`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$useBillingAddressForTax](commerce4:craft\commerce\models\Settings::$useBillingAddressForTax)

</div>

Whether taxes should be calculated based on the billing address instead of the shipping address.



### `validateBusinessTaxIdAsVatId`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$validateBusinessTaxIdAsVatId](commerce4:craft\commerce\models\Settings::$validateBusinessTaxIdAsVatId)

</div>

Whether to enable validation requiring the `businessTaxId` to be a valid VAT ID.

When set to `false`, no validation is applied to `businessTaxId`.

When set to `true`, `businessTaxId` must contain a valid VAT ID.

::: tip
This setting strictly toggles input validation and has no impact on tax configuration or behavior elsewhere in the system.
:::



## Payments

### `allowPartialPaymentOnCheckout`

<div class="compact">

Allowed types
:  [boolean](https://php.net/language.types.boolean)

Default value
:  `false`

Defined by
:  [Settings::$allowPartialPaymentOnCheckout](commerce4:craft\commerce\models\Settings::$allowPartialPaymentOnCheckout)

</div>

Whether [partial payment](making-payments.md#checkout-with-partial-payment) can be made from the front end when the gateway allows them.

The `false` default does not allow partial payments on the front end.



### `gatewayPostRedirectTemplate`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `''`

Defined by
:  [Settings::$gatewayPostRedirectTemplate](commerce4:craft\commerce\models\Settings::$gatewayPostRedirectTemplate)

</div>

The path to the template that should be used to perform POST requests to offsite payment gateways.

The template must contain a form that posts to the URL supplied by the `actionUrl` variable and outputs all hidden inputs with
the `inputs` variable.

```twig
<!DOCTYPE html>
<html>
<head>
  <meta http-equiv="Content-Type" content="text/html; charset=UTF-8">
  <title>Redirecting...</title>
</head>
<body onload="document.forms[0].submit();">
<form action="{{ actionUrl }}" method="post">
  <p>Redirecting to payment page...</p>
  <p>
    {{ inputs|raw }}
    <button type="submit">Continue</button>
  </p>
</form>
</body>
</html>
```

::: tip
Since this template is simply used for redirecting, it only appears for a few seconds, so we suggest making it load fast with minimal
images and inline styles to reduce HTTP requests.
:::

If empty (default), each gateway will decide how to handle after-payment redirects.



### `paymentCurrency`

<div class="compact">

Allowed types
:  [array](https://php.net/language.types.array), [null](https://php.net/language.types.null)

Default value
:  `null`

Defined by
:  [Settings::$paymentCurrency](commerce4:craft\commerce\models\Settings::$paymentCurrency)

</div>

ISO codes for supported payment currencies.

See [Payment Currencies](payment-currencies.md).



## Units

### `dimensionUnits`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'mm'`

Defined by
:  [Settings::$dimensionUnits](commerce4:craft\commerce\models\Settings::$dimensionUnits)

</div>

Unit type for dimension measurements.

Options:

- `'mm'`
- `'cm'`
- `'m'`
- `'ft'`
- `'in'`



### `weightUnits`

<div class="compact">

Allowed types
:  [string](https://php.net/language.types.string)

Default value
:  `'g'`

Defined by
:  [Settings::$weightUnits](commerce4:craft\commerce\models\Settings::$weightUnits)

</div>

Units to be used for weight measurements.

Options:

- `'g'`
- `'kg'`
- `'lb'`




<!-- END SETTINGS -->

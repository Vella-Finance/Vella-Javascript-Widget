# Vella Checkout Vanilla Javascript

This is a simple HTML and vanilla Javascript implementation of the Vella Checkout widget. To get started:

## Step 1: Clone this repository

e.g _Using HTTPS_:

```
git clone https://github.com/Vella-Finance/Vella-Javascript-Widget.git
```

_Alternatively, if you use ssh_:

```
git clone git@github.com:Vella-Finance/Vella-Javascript-Widget.git
```

## Step 2: Update your api key

Open the `index.html` file in your preferred text editor, update the config object with your public key gotten from the [Vella Dashboard](https://app.vella.finance) under settings page.

```javascript
const key = ""; // your vella API test/live key
const config = {
  email: "example@mail.com", // string - customer email
  name: "Tade Ogidan", // string - customer name
  amount: 100.0, //float - amount to pay
  currency: "NGN", // supported currency  NGN USD,GBP,USDT,USDC
  merchant_id: "", // string - merchant id
  reference: "", // string - generated reference
  custom_meta: [], // custom meta data,
  source: "", // domain or location name widget is being called from
};
const vellaSDK = VellaCheckoutSDK.init(key, config);
vellaSDK.onSuccess((response) => {
  console.log("data", response); // success response with data
});
vellaSDK.onError((error) => {
  console.log("error", error); // error response
});
vellaSDK.onClose(() => {
  console.log("widget closed"); // trigger close
});
```

## Support

If you're having trouble with Vella checkout integration, please reach out to us at hello@vella.finance or come chat with us using on https://app.vella.finance. We're happy to help you out with your integration to Vella.

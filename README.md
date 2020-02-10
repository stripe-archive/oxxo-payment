# Paying with OXXO or Cards on the web 
Stripe users in Mexico can accept OXXO payments from customers in Mexico by using the Payment Intents and Payment Methods APIs. Customers pay with OXXO by providing a generated number and cash payment at an OXXO store. Stripe will notify you when the payment is completed.

The [Payment Intents API](https://stripe.com/docs/api/payment_intents) makes it simple to accept multiple payment methods on the web. You can build a payment form that easily handles payment methods like OXXO alongside simpler flows like cards. 

This sample shows how to:

* 🏦💳 Accept OXXO and card payments
* 👂 Set up a webhook to listen for events
* 💁‍ Handle next actions for displaying OXXO voucher details

## How to run locally

This sample includes 4 server implementations in Node, Ruby, Python, and PHP. 

Follow the steps below to run locally.

**1. Clone and configure the sample**
You can clone the sample here:

```
git clone https://github.com/fay-stripe/web-oxxo-payments
```

Copy the .env.example file into a file named .env in the folder of the server you want to use. For example:

```
cp .env.example server/node/.env
```

You will need a Stripe account in order to run the demo. Once you set up your account, go to the Stripe [developer dashboard](https://stripe.com/docs/development#api-keys) to find your API keys.

```
STRIPE_PUBLISHABLE_KEY=<replace-with-your-publishable-key>
STRIPE_SECRET_KEY=<replace-with-your-secret-key>
```

`STATIC_DIR` tells the server where to the client files are located and does not need to be modified unless you move the server files.

**2. Follow the server instructions on how to run:**

Pick the server language you want and follow the instructions in the server folder README on how to run.

For example, if you want to run the Node server:

```
cd server/node # there's a README in this folder with instructions
npm install
npm start
```

**3. [Optional] Run a webhook locally:**

If you want to test with a local webhook on your machine, you can use the Stripe CLI to easily spin one up.

First [install the CLI](https://stripe.com/docs/stripe-cli) and [link your Stripe account](https://stripe.com/docs/stripe-cli#link-account).

```
stripe listen --forward-to localhost:4242/webhook
```

The CLI will print a webhook secret key to the console. Set `STRIPE_WEBHOOK_SECRET` to this value in your .env file.

You should see events logged in the console where the CLI is running.

When you are ready to create a live webhook endpoint, follow our guide in the docs on [configuring a webhook endpoint in the dashboard](https://stripe.com/docs/webhooks/setup#configure-webhook-settings). 


## FAQ
Q: Why did you pick these frameworks?

A: We chose the most minimal framework to convey the key Stripe calls and concepts you need to understand. These demos are meant as an educational tool that helps you roadmap how to integrate Stripe within your own system independent of the framework.

Q: Can you show me how to build X?

A: We are always looking for new sample ideas, please email dev-samples@stripe.com with your suggestion!

## Author(s)
[@fay-stripe](https://twitter.com/mfaywu)

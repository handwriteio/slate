# Introduction

> API Endpoint:

```
https://api.handwrite.io/v1/
```

Welcome to the Handwrite API!

You can use our API to send handwritten notes in an automated manner, using our REST endpoints.

We have language bindings in Shell and JavaScript, with Python and Ruby coming soon!

If you have questions or feedback please feel free to reach out to us [here](https://www.handwrite.io/contact).

# Getting Started

Handwrite uses API keys to allow access to the API. You must first sign up for a Handwrite account to obtain an API key. You will be charged per card based on the plan you choose.

Once you're logged in, you can create a key by going to the [developer dashboard](https://app.handwrite.io/integrations/api).

You'll notice when you create a key that it will start with `test_hw` or `live_hw`. Test keys will not count against your usage and can be used for testing purposes as you might have guessed!

An API key is expected to be included in all API requests to the server in a header that looks like the following:

`Authorization: live_hw_sid92ldkasiie299dkw`

Also, the content type must be `Content-Type: application/json`

<aside class="notice">Please note: you cannot make requests from the browser as your API token would be exposed publicly.</aside>

# Endpoints

## Get Handwritings

> The Request

```shell
curl --request GET \
  --url https://api.handwrite.io/v1/handwriting \
  --header 'authorization: test_hw_54838bde67e8e6255fa6' \
  --header 'content-type: application/json'
```

```javascript
const request = require("request");

const options = {
  method: "GET",
  url: "https://api.handwrite.io/v1/handwriting",
  headers: {
    "content-type": "application/json",
    authorization: "test_hw_54838bde67e8e6255fa6"
  }
};

request(options, (error, response, body) => {
  if (error) throw new Error(error);

  console.log(body);
});
```

> The Response - An array of handwriting objects in JSON format

```json
[
  {
    "_id": "5db6f0724cc1751452c5ae8e",
    "name": "Jeremy",
    "preview_url": "http://res.cloudinary.com/handwrite/image/upload/v1572270190/cards/wkwtnagsty79e0tlbiad.jpg"
  },
  {
    "_id": "5db6f08c4cc1751452c5ae8f",
    "name": "Tribeca",
    "preview_url": "http://res.cloudinary.com/handwrite/image/upload/v1572270217/cards/hs92dvha3i5bvuhnboz7.jpg"
  },
  {
    "_id": "5db6f0f14cc1751452c5ae90",
    "name": "Terry",
    "preview_url": "http://res.cloudinary.com/handwrite/image/upload/v1572270316/cards/bjocrcfhed6dwdadbtpv.jpg"
  }
]
```

This will fetch handwriting options for your users to preview and choose from.

![Handwriting examples](https://res.cloudinary.com/handwrite/image/upload/c_scale,q_70,w_600/v1572557097/assets/hws_ioi6vp.png "Handwriting examples")

### HTTP Request

`POST https://api.handwrite.io/v1/handwriting`

## Get Stationery

> The Request

```shell
curl --request GET \
  --url https://api.handwrite.io/v1/stationery \
  --header 'authorization: test_hw_54838bde67e8e6255fa6' \
  --header 'content-type: application/json'
```

```javascript
const request = require("request");

const options = {
  method: "GET",
  url: "https://api.handwrite.io/v1/stationery",
  headers: {
    "content-type": "application/json",
    authorization: "test_hw_54838bde67e8e6255fa6"
  }
};

request(options, (error, response, body) => {
  if (error) throw new Error(error);

  console.log(body);
});
```

> The Response - An array of stationery objects in JSON format

```json
[
  {
    "_id": "5db6f1854cc1751452c5ae93",
    "name": "Classic White",
    "preview_url": "http://res.cloudinary.com/handwrite/image/upload/v1572270464/cards/yflijfai9wm38czthluk.jpg"
  },
  {
    "_id": "5db6f19b4cc1751452c5ae95",
    "name": "Classic Navy",
    "preview_url": "http://res.cloudinary.com/handwrite/image/upload/v1572270484/cards/afwlmwfs4dkh5s6xt5uc.jpg"
  },
  {
    "_id": "5db6f1b74cc1751452c5ae96",
    "name": "Hello",
    "preview_url": "http://res.cloudinary.com/handwrite/image/upload/v1572270512/cards/mb9fhgwgnkdxiqtr9k0i.jpg"
  }
]
```

This will fetch any custom stationery you have uploaded as well as the publicly available options we provide.

<!-- https://res.cloudinary.com/handwrite/image/upload/c_scale,q_66,w_500/v1572556446/assets/cards_ddb23v.png -->

![Stationery examples](https://res.cloudinary.com/handwrite/image/upload/c_scale,q_70,w_600/v1572556446/assets/cards_ddb23v.png "Stationery examples")

### HTTP Request

`GET https://api.handwrite.io/v1/stationery`

## Send a Letter

> The Request

```shell
curl --request POST \
  --url https://api.handwrite.io/v1/send \
  --header 'authorization: test_hw_54838bde67e8e6255fa6' \
  --header 'content-type: application/json' \
  --data '{
  "text": "Hey dude,\nIt was great meeting you last week at the party. We'\''d love to have you back at the next one!\n\nBest,\n-Jackie",
  "handwriting": "5db6f0724cc1751452c5ae8e",
  "card": "5db6f0724cc1751452c5ae8e",
  "recipients": [
    {
      "firstName": "The",
      "lastName": "Dude",
      "company": "Unemployed",
      "street1": "25 Main Street",
      "city": "Los Angeles",
      "state": "CA",
      "zip": "90210"
    }
  ],
  "from": {
    "firstName": "Jackie",
		"lastName": "Treehorn",
    "street1": "1 Random Street",
    "street2": "Apt 33A",
    "city": "Malibu",
    "state": "CA",
    "zip": "90263"
  }
}'
```

```javascript
const request = require("request");

const options = {
  method: "POST",
  url: "https://api.handwrite.io/v1/send",
  headers: {
    "content-type": "application/json",
    authorization: "test_hw_54838bde67e8e6255fa6"
  },
  body: {
    text:
      "Hey dude,\nIt was great meeting you last week at the party. We'd love to have you back at the next one!\n\nBest,\n-Jackie",
    handwriting: "5db6f0724cc1751452c5ae8e",
    card: "5db6f0724cc1751452c5ae8e",
    recipients: [
      {
        firstName: "The",
        lastName: "Dude",
        company: "Unemployed",
        street1: "25 Main Street",
        city: "Los Angeles",
        state: "CA",
        zip: "90210"
      }
    ],
    from: {
      firstName: "Jackie",
      lastName: "Treehorn",
      street1: "1 Random Street",
      street2: "Apt 33A",
      city: "Malibu",
      state: "CA",
      zip: "90263"
    }
  },
  json: true
};

request(options, (error, response, body) => {
  if (error) throw new Error(error);

  console.log(body);
});
```

> The Response - An array of <code>orders</code> in JSON format

```json
[
  {
    "_id": "5dba45e8f2b173cb5dff0300",
    "to": {
      "firstName": "The",
      "lastName": "Dude",
      "company": "Unemployed",
      "street1": "25 Main Street",
      "city": "Los Angeles",
      "state": "CA",
      "zip": "90210"
    },
    "from": {
      "firstName": "Jackie",
      "lastName": "Treehorn",
      "street1": "1 Random Street",
      "street2": "Apt 33A",
      "city": "Malibu",
      "state": "CA",
      "zip": "90263"
    },
    "status": "processing",
    "handwriting": "5db6f0724cc1751452c5ae8e",
    "card": "5db6f0724cc1751452c5ae8e",
    "createdAt": "2019-10-31T02:24:40.648Z"
  }
]
```

Send a letter to between 1 and 1000 recipients at once. For higher limits, contact us.

### HTTP Request

`POST https://api.handwrite.io/v1/send`

### Request parameters

| Parameter                                 | Type   | Description                                                                                                |
| ----------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------- |
| text <em>required</em>                    | String | This is the body of the letter. Maximum of 320 characters.                                                 |
| card <em>required</em>                    | String | ID of the stationery/card you want. This will also determine whether it is the front or back of card.      |
| handwriting <em>required</em>             | String | ID of the handwriting you want to use.                                                                     |
| recipients <em>required</em>              | Array  | List of recipient objects. Must have at least one, but can be up to 1000.                                  |
| recipients[n].firstName <em>required</em> | String | Recipient first name                                                                                       |
| recipients[n].lastName                    | String | Recipient last name                                                                                        |
| recipients[n].company                     | String | Recipient company. If this is included, company will be on the first line, with attention to on the second |
| recipients[n].street1 <em>required</em>   | String | First line of the address, e.g. 555 Terrance Street                                                        |
| recipients[n].street2                     | String | Second line of the address, e.g. Apt. 201                                                                  |
| recipients[n].city <em>required</em>      | String |
| recipients[n].state <em>required</em>     | String | \*Must be the capitalized two digit abbreviation, e.g. AL instead of Alabama                               |
| recipients[n].zip <em>required</em>       | String | Must be exactly 5 characters                                                                               |
| from                                      | Object | Return address. (optional)                                                                                 |
| from.firstName                            | String |
| from.lastName                             | String |
| from.street1                              | String |
| from.street2                              | String |
| from.city                                 | String |
| from.state                                | String |
| from.zip                                  | String |

<aside class="success">
You're doing great — If we can do anything to help, email us at api@handwrite.io
</aside>

### Merge Variables

Sometimes you'll want to send a card to many people with slightly different text on each one. For example, you might want to address each recipient by his or her first name.

In order to do this, you'll use "merge variables."

`Hey {firstName}, I hope all is well down in {city}! How's business at {company} these days?`

In this case, each occurrence of {firstName} will be replaced with the recipient's actual first name.

We support the following merge variables currently, with more coming in the future including custom merge variables:

- first name: `{firstName}`
- last name: `{lastName}`
- company: `{company}`
- city: `{city}`
- state: `{state}`

# Send a Letter

## One or Many Recipients

> The Request

```shell
curl --request POST \
  --url https://api.handwrite.io/v1/send \
  --header 'authorization: test_hw_54838bde67e8e6255fa6' \
  --header 'content-type: application/json' \
  --data '{
  "text": "Hey dude,\nIt was great meeting you last week at the party. We'\''d love to have you back at the next one!\n\nBest,\n-Jackie",
  "handwritingId": "5db6f0724cc1751452c5ae8e",
  "cardId": "5db6f0724cc1751452c5ae8e",
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
    handwritingId: "5db6f0724cc1751452c5ae8e",
    cardId: "5db6f0724cc1751452c5ae8e",
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
    "handwritingId": "5db6f0724cc1751452c5ae8e",
    "cardId": "5db6f0724cc1751452c5ae8e",
    "createdAt": "2019-10-31T02:24:40.648Z"
  }
]
```

Send a letter to between 1 and 1000 recipients at once. For higher limits, contact us.

### HTTP Request

`POST https://api.handwrite.io/v1/send`

### Send attributes

| Parameter                                 | Type   | Description                                                                                                |
| ----------------------------------------- | ------ | ---------------------------------------------------------------------------------------------------------- |
| text <em>required</em>                    | String | This is the body of the letter. Maximum of 320 characters.                                                 |
| cardId <em>required</em>                  | String | ID of the stationery/card you want. This will also determine whether it is the front or back of card.      |
| handwritingId <em>required</em>           | String | ID of the handwriting you want to use.                                                                     |
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

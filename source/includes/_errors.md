# Response Codes

Handwrite uses conventional HTTP response codes to indicate the success or failure of an API request. In general: Codes in the `2xx` range indicate success. Codes in the `4xx` range indicate an error that failed given the information provided (e.g., a required parameter was omitted or was the incorrect type, etc.). Codes in the `5xx` range indicate an error with our servers.

The Handwrite API uses the following response codes:

| Error Code | Meaning                                                                                   |
| ---------- | ----------------------------------------------------------------------------------------- |
| 200        | Success. Everything worked as expected                                                    |
| 400        | Bad Request -- Your request is invalid.                                                   |
| 401        | Unauthorized -- Your API key is wrong.                                                    |
| 404        | Not Found -- The specified resource could not be found.                                   |
| 429        | Too Many Requests -- You're requesting too much! Slow down!                               |
| 500        | Internal Server Error -- We had a problem with our server. Try again later.               |
| 503        | Service Unavailable -- We're temporarily offline for maintenance. Please try again later. |

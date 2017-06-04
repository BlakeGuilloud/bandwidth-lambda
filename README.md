## bandwidth-lambda

An ongoing project to explore serverless architecture through the texting services that the Bandwidth API provides.

### Send
The send route accepts two parameters, `to (String)` and `message (String)`, constructs a request for bandwidth, and sends it off for the Bandwidth API to take over.

Example request:
```javascript
const rp = 'request-promise';

const options = {
  method: 'POST',
  uri: 'apigatewayroute',
  body: {
    to: '+18438126962',
    message: 'Hello Blake!'
  },
  json: true
}

rp(options)
  .then(handleSuccess)
  .catch(handleError);
```

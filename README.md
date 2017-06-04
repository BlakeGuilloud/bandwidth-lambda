## bandwidth-lambda - +18437329699

An ongoing project to explore serverless architecture through the texting services that the Bandwidth API provides.

### Disclaimer:
I am having issues hitting API Gateway with my REST client, Insomnia.. It appears to be working fine with Postman, but getting a cloud front rejection when using Insomnia.

### Routes:
 - send
    - POST: 'https://9agao47h5d.execute-api.us-west-2.amazonaws.com/prod/bandwidth-lambda_send'

### send
The send route accepts two parameters, `to (String)` and `message (String)`, constructs a request for bandwidth, and sends it off for the Bandwidth API to take over.

Example NodeJS request:
```javascript
const rp = 'request-promise';

const options = {
  method: 'POST',
  uri: 'https://9agao47h5d.execute-api.us-west-2.amazonaws.com/prod/bandwidth-lambda_send',
  body: {
    to: '+18438126962',
    text: 'Hello Blake!'
  },
  json: true
};

rp(options)
  .then(handleSuccess)
  .catch(handleError);
```
Example client request with axios:
```javascript
const axios = require('axios');

const uri = 'https://9agao47h5d.execute-api.us-west-2.amazonaws.com/prod/bandwidth-lambda_send';
const body = {
  to: '+18438126962',
  text: 'Hello Blake!'
};

axios.post(uri, body)
  .then(handleSuccess)
  .catch(handleError);
```

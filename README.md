# facebook-conversion-tag-server-side
Facebook Conversion tag for GTM Server Side tracking with monitoring capabilities for failed requests.

### Error logging works as following (not required):

1. Whenever the Facebook API doesn't return a successful HTTP status code (200-299)
2. The failed request can be sent with an HTTP POST to an external monitoring platform.

### How should my external platform deal with the POST request?

This tag sends the request (POST) as a stringified JSON object containing the following properties:
1. requestHeaders
2. statusCode
3. payload
4. customerDomain
5. endpointUrl
6. initialResponse

#### requestHeaders
Contains the HTTP request headers of the unsuccessful request.

#### statusCode
The status code of the unsuccessful request.

#### payload
The data of the unsuccessful request.

#### customerDomain
Domain of GTM Server Side Tagging container.

#### endpointUrl
The endpoint URL of the unsuccessful request.

#### initialResponse
The returned response from the unsuccessful request.

### Why is this useful?
You could retry these request when monitoring on an external platform preventing/minimizing valuable data loss because of expired API tokens or downtime. 

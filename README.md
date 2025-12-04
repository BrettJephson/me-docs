---
description: Test description
---

# Page 123

## H1 (should render h2)

### H2 (should render h3)

#### Test h3 123 (should render h4)

{% code lineNumbers="true" %}
````json
{
  "export": {
    "date": "2025-02-27T14:11:38.684449698Z",
    "apimVersion": "4.7.0-SNAPSHOT"
  },
  "api": {
    "definitionVersion": "V4",
    "type": "PROXY",
    "listeners": [
      {
        "type": "HTTP",
        "paths": [
          {
            "path": "/0205-javascript/",
            "overrideAccess": false
          }
        ],
        "entrypoints": [
          {
            "type": "http-proxy",
            "qos": "AUTO",
            "configuration": {}
          }
        ]
      }
    ],
    "endpointGroups": [
      {
        "name": "Default HTTP proxy group",
        "type": "http-proxy",
        "loadBalancer": {
          "type": "ROUND_ROBIN"
        },
        "sharedConfiguration": "{\"proxy\":{\"useSystemProxy\":false,\"enabled\":false},\"http\":{\"keepAliveTimeout\":30000,\"keepAlive\":true,\"followRedirects\":false,\"readTimeout\":10000,\"idleTimeout\":60000,\"connectTimeout\":3000,\"useCompression\":true,\"maxConcurrentConnections\":20,\"version\":\"HTTP_1_1\",\"pipelining\":false},\"ssl\":{\"keyStore\":{\"type\":\"\"},\"hostnameVerifier\":true,\"trustStore\":{\"type\":\"\"},\"trustAll\":false}}",
        "endpoints": [
          {
            "name": "Default HTTP proxy",
            "type": "http-proxy",
            "weight": 1,
            "inheritConfiguration": true,
            "configuration": {
              "target": "https://api.gravitee.io/whattimeisit"
            },
            "sharedConfigurationOverride": "{}",
            "services": {},
            "secondary": true
          }
````
{% endcode %}

{% hint style="info" %}
**test h3 123 test (should render h4)**

test
{% endhint %}

{% code overflow="wrap" %}
`````typescript
````
function test () {
  console.log("SOMETHING");
}
// test

```typescript
<strong>// test
</strong>
```

```javascript
function test() { const str = "test"; }
```
````
````

</div>

````typescript
// test
```
function test() {
  // this is a test
}
```
````

<div data-gb-custom-block data-tag="code" data-overflow='wrap'>

````
test
```javascript
function test() { }
```
````

</div>

1. Log in.
2. Click **Settings > Providers**.
3. Select.
4.  Map `telephoneNumber` to a new user attribute named `telephone_number`.

    <figure><img src="https://docs.gravitee.io/images/am/current/graviteeio-am-userguide-idp-user-mappers-phoneno.png" alt=""><figcaption><p>LDAP user mappers</p></figcaption></figure>
5.  Get the User Profile information via the UserInfo Endpoint and you will see that the new user attribute is present.

    {% code overflow="wrap" %}

    ```sh
    curl -X GET http://TEST-HOST/:securityDomainPath/oidc/userinfo -H 'Authorization: Bearer :accessToken'
    ```

    {% endcode %}

    If it is working correctly, you will see something like this:

    ````sh
    HTTP/1.1 200 OK
    Content-Type: application/json;charset=UTF-8
    Cache-Control: no-cache, no-store, max-age=0, must-revalidate
    Pragma: no-cache
    {
        "uid": "johndoe",
        "given_name": "John",
        "family_name": "Doe"
        "telephone_number: "202-555-0105"
    }
    ```The same principle applies to any identity provider.
    ````
`````
{% endcode %}

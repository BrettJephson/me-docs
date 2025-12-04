---
description: Test description
---

# Page 123

## H1 (should render h2)

### H2 (should render h3)

#### Test h3 123 (should render h4)

{% hint style="info" %}
#### test h3 123 test  (should render h4)

test
{% endhint %}

<pre class="language-javascript" data-overflow="wrap"><code class="lang-javascript">function test () {
  console.log("SOMETHING");
}
// test
````typescript
<strong>// test
</strong>```javascript
function test() { const str = "test"; }
```
````
</code></pre>

````typescript
// test
```
function test() {
  // this is a test
}
```
````

{% code overflow="wrap" %}
````
test
```javascript
function test() { }
```
````
{% endcode %}

1. Log in.
2. Click **Settings > Providers**.
3. Select.
4.  Map `telephoneNumber` to a new user attribute named `telephone_number`.



    <figure><img src="https://docs.gravitee.io/images/am/current/graviteeio-am-userguide-idp-user-mappers-phoneno.png" alt=""><figcaption><p>LDAP user mappers</p></figcaption></figure>
5.  Get the User Profile information via the UserInfo Endpoint and you will see that the new user attribute is present.

    {% code overflow="wrap" %}
    ```sh
    curl -X GET http://GRAVITEEIO-AM-GATEWAY-HOST/:securityDomainPath/oidc/userinfo -H 'Authorization: Bearer :accessToken'
    ```
    {% endcode %}

    If it is working correctly, you will see something like this:

    ```sh
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
    ```

The same principle applies to any identity provider.

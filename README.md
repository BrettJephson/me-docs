---
description: Test description
---

# Page 123

## H1 (should render h2)

### H2 (should render h3)

#### Test h3 123 (should render h4)

1. Log in to AM Console.
2. Click **Settings > Providers**.
3. Select your LDAP identity provider and click the **User mappers** tab.
4.  Map your LDAP (raw) attribute `telephoneNumber` to a new user attribute named `telephone_number`.

    <figure><img src="https://docs.gravitee.io/images/am/current/graviteeio-am-userguide-idp-user-mappers-phoneno.png" alt=""><figcaption><p>LDAP user mappers</p></figcaption></figure>
5.  Get the User Profile information via the UserInfo Endpoint and you will see that the new user attribute is present.

    <pre class="language-sh" data-overflow="wrap"><code class="lang-sh">curl -X GET http://GRAVITEEIO-AM-GATEWAY-HOST/:securityDomainPath/oidc/userinfo -H 'Authorization: Bearer :accessToken'
    </code></pre>

    If it is working correctly, you will see something like this:

    ```sh
    HTTP/1.1 200 OK
    Content-Type: application/json;charset=UTF-8
    Cache-Control: no-cache, no-store, max-age=0, must-revalidate
    Pragma: no-cache
    {
        "uid": "johndoe",
        "given_name": "John",
        "family_name": "Doe",
        "telephone_number: "202-555-0105"
    }
    ```

The same principle applies to any identity provider.

{% code lineNumbers="true" %}
```json
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
```
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
`````
{% endcode %}

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

# Cache

The **Cache** action allows developers to interact with the store's Mechanic [**cache**](../../platform/cache/), using commands inspired by Redis. Cache entries have a **key**, a **value** containing up to 256 kilobytes, and a **ttl** value ("Time To Live") in seconds, defaulting to the maximum of 60 days (i.e. 5184000 seconds).

{% hint style="info" %}
Cache actions (like all actions) are performed after their task run is completed. The results of Cache actions therefore aren't reflected during the task run that generates them.
{% endhint %}

## Options

This action supports two styles of options: a more verbose nested structure, and a simpler set of positional arguments.

All commands must define a cache key, matching the regular expression `/^[a-z0-9_:\-\.\/]+$/i`.

### Verbose options

In this option style, the cache command is given as the root key of the options object. The root value is itself an option, containing the arguments needed for the selected cache command.

{% tabs %}
{% tab title="Liquid" %}
```liquid {% action "cache" %} { "incr": { "key": "foo", "ttl": 600 } } {% endaction %} ```
{% endtab %}
{% endtabs %}

### Positional options

In this option style, the cache command and its arguments are given in a list. Use the cache command reference below to find the argument order required for each command.

{% tabs %}
{% tab title="Liquid" %}
```liquid {% action "cache", "incr", "foo" %} ```
{% endtab %}
{% endtabs %}

## Expiration

Each cache entry is given a default TTL value of 60 days, or 5184000 seconds. (A cache entry's TTL may not exceed 60 days.)

A cache command will always reset the entry's TTL value upon execution, regardless of the TTL's original value.

## Commands

The required arguments for each command are given below, in the order in which they are supported for [positional options](cache.md#positional-options).

When a command is given using [verbose options](cache.md#verbose-options), the `ttl` value (in seconds) is always supported.

### set

Stores a value. Requires `key` and `value`. The stored value may be any JSON object.

### setex

Using a defined TTL (an expiration interval) given in seconds, stores a value. Requires `key`, `ttl`, and `value`. The stored value may be any JSON object.

{% hint style="info" %}
The "setex" command has the same net functionality as "set", but it does have one difference: because "setex" requires an explicit \`ttl\` value, it's possible to use "setex" to express an expiring value using a single line of Liquid. The same result could be achieved with "set", but it would require using verbose options.

```liquid
{% action "cache", "setex", "foo", 5, "bar" %}
```
{% endhint %}

### del

Deletes a stored key. Requires `key`.

### incr

Increments a numeric key by 1. Requires `key`. If the key is not already set, the value before incrementing will be assumed to be 0.

### incrby

Increments a numeric key by the value of your choice. Requires `key`, and an integer `increment`. If the key is not already set, the value before incrementing will be assumed to be 0.

### decr

Decrements a numeric key by 1. Requires `key`. If the key is not already set, the value before incrementing will be assumed to be 0.

### decrby

Decrements a numeric key by the value of your choice. Requires `key`, and an integer `decrement`. If the key is not already set, the value before incrementing will be assumed to be 0.

## Examples

### Set a value, auto-expiring in 60 days

{% tabs %}
{% tab title="Verbose options" %}
```liquid 
{% action "cache" %} { "set": { "key": "foo", "value": 5 } } {% endaction %}
```
{% endtab %}

{% tab title="Positional options" %}
```liquid
{% action "cache", "set", "foo", 5 %}
```
{% endtab %}
{% endtabs %}

### Set a value, explicitly expiring in 1 minute

{% tabs %}
{% tab title="Verbose options" %}
```liquid 
{% action "cache" %}
{ "setex": { "key": "foo", "ttl": 60, "value": 5 } }
{% endaction %}
```
{% endtab %}

{% tab title="Positional options" %}
```liquid 
{% action "cache", "setex", 60, "foo" %}
```
{% endtab %}
{% endtabs %}

### Clear a value

{% tabs %}
{% tab title="Verbose options" %}
```liquid
{% action "cache" %} { "del": { "key": "foo" } } {% endaction %}
```
{% endtab %}

{% tab title="Positional options" %}
```liquid 
{% action "cache", "del", "foo" %}
```
{% endtab %}
{% endtabs %}

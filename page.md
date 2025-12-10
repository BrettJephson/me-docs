# Page test

In this option style, the cache command is given as the root key of the options object. The root value is itself an option, containing the arguments needed for the selected cache command.

Test

{% tabs %}
{% tab title="Liquid" %}
```liquid
{% action "cache" %}
  {
    "incr": {
      "key": "foo",
      "ttl": 600
    }
  }
{% endaction %}
```
{% endtab %}
{% endtabs %}

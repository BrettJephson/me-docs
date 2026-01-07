---
description: Test description
---

# Page Main

{% tabs %}
{% tab title="Liquid" %}
```liquid
{% action "cache" %}
  {
    "incr": {
      "key": "foo",
      "ttl": 601
    }
  }
{% endaction %}
```
{% endtab %}
{% endtabs %}

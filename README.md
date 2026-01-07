---
description: Test description
---

# Page 123

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

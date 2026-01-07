---
description: Test description
---

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

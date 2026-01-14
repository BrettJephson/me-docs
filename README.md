---
description: Test description
---

# Page Main

This is a test? Test 125 <a class="button primary">Buttontest</a>\
test

## tThis is a test? Test 12

test



<table><thead><tr><th></th><th width="249.99609375"></th><th></th></tr></thead><tbody><tr><td>Test</td><td><h4>Test 1234</h4><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>Test</p></div></td><td><pre class="language-typescript"><code class="lang-typescript">// Code block
</code></pre></td></tr><tr><td>Test 123 test <code>code</code></td><td><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>test 12345</p></div></td><td><blockquote><p>test</p></blockquote></td></tr></tbody></table>

TESTING:

{% hint style="warning" %}
The test 123 [Shopify variables](code/environment-variables.md#shopify-variables) available to tasks always contain data drawn from the event itself. If a task has a offset event subscription, this data may be outdated by the time the task runs. The [Shopify variables](code/environment-variables.md#shopify-variables) available to tasks always contain data drawn from the event itself. If a task has a offset event subscription, this data may be outdated by the time the task runs.

To test the data in a Shopify variable, use something like this:

```liquid
{% unless event.preview %}
  {% assign customer = customer.reload %}
{% endunless %}
```

Remember, Mechanic does not permit access to the Shopify API during [event preview](previews/). Using this `unless` statement ensures that reloading only happens during a live event.
{% endhint %}

{% tabs %}
{% tab title="Liquid" %}
Test 1

```liquid
{% action "cache" %}
  {
    "incr": {
      "key": "foo",
      "ttl": 607
    }
  }
{% endaction %}
```

Test 2
{% endtab %}
{% endtabs %}

{% tabs %}
{% tab title="Not Liquid" %}
```actionscript-3
function test() {
    // test 223
}
```

Test 23
{% endtab %}
{% endtabs %}

---
description: Test description
---

# Page Main

## Page Main

{% tabs %}
{% tab title="tool" %}

{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

This is a test? Test 125 <a class="button primary">Buttontest</a>\
test

### tThis is a test? Test&#x20;

<details>

<summary>ytest</summary>



</details>

test

<table><thead><tr><th>heloo</th><th width="249.99609375"></th><th></th></tr></thead><tbody><tr><td>Test</td><td><p><strong>Test 1234</strong></p><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>Test</p></div></td><td><pre class="language-typescript"><code class="lang-typescript">// Code block
</code></pre></td></tr><tr><td>Test 123 test <code>code</code></td><td><div data-gb-custom-block data-tag="hint" data-style="info" class="hint hint-info"><p>test 12345</p></div></td><td><blockquote><p>test</p></blockquote></td></tr></tbody></table>

TESTING 123:

{% hint style="info" %}
The \[Shitify variables]\(environment-variables.md#shopify-variables) available to tasks always contain data drawn from the event itself. If a task has a offset event subscription, this data may be outdated by the time the task runs.

Decode the base64-encoded request body with Liquid, using Mechanic's to \[decode\\\_base64]\(liquid/filters/#base64-decode\_bass64) filter.

```liquid
{% assign raw_request_body = event.data.body_base64 | decode_base64 %}
```
{% endhint %}

## Data types

In Liquid, different kinds of data have different **types**. Each type describes the nature of its data.

{% hint style="warning" %}
Some of the documentation below is specific to Mechanic Liquid, and may not apply to Shopify Liquid, or to other Liquid implementations.
{% endhint %}

### String

A string contains a series of characters, forming text.

```liquid
{% assign my_name = "Matt" %}
```

### Integer, Float

Liquid supports both two number types: integers (whole numbers) and floats (numbers having decimal precision).

```liquid
{% assign a_int = 99 %}
{% assign a_float = 99.99 %}
```

### Boolean

```liquid
{% assign is_mechanic_awesome = true %}
{% assign is_it_warm_outside = false %}
```

### Nil

Borrowing from [Ruby's concept of nil](https://www.rubyguides.com/2018/01/ruby-nil/), Liquid's `nil` is an empty value that is returned when Liquid code has no results. It evaluates to `false` in conditionals statements, and outputs nothing when printing out text.

{% hint style="warning" %}
If a variable reference comes up missing, Liquid will silently use `nil` instead _without_ raising an error.
{% endhint %}

{% hint style="info" %}
In Liquid, `null` is not a keyword literal. But, because `null` is also typically not used as a variable name in Mechanic Liquid code, and because Liquid uses `nil` when a variable is not found, it works out: `{% assign foo = null %}` results in assigning `foo` a value of `nil`. (Unless, of course, `null` was previously assigned to something else, e.g. `{% assign null = "something else" %}`.)
{% endhint %}

{% tabs %}
{% tab title="Gitbook Root" %}
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

## Test <a href="#root" id="root"></a>

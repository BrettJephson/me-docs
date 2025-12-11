---
description: Test description
---

# Page 123

1. Open your `gravitee.yml` file.
   1.
2. test
3.  In the `http.cookie` section, update the `secure` value:

    <pre class="language-yaml" data-title="gravitee.yml" data-overflow="wrap"><code class="lang-yaml">#http
    ##  cookie:
    #    secure: false # Default is false for demonstration purpose but we highly recommend you to enable cookie secure.
    #    sameSite: Lax
    #    session:
    #      name: session-name
    #      timeout: 1800000 # (in milliseconds)
    </code></pre>
4. You can also consider updating the \`sameSite\` to \[Strict]\(https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Set-Cookie#syntax) and adapt the session timeout:

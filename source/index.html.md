---
title: Exbito API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a href='https://exbito.com/'>Exbito Website</a>
  - <a href='https://app.exbito.com/register'>Exbito Web App</a>
  - <a href='https://play.google.com/store/apps/details?id=com.exbito.app'>Exbito Android App</a>
  - <a href='https://exbito.com/fees'>Exchange Fee Rates</a>
  - <a href='https://status.exbito.com/'>Service Status</a>
  - <a href='https://github.com/Exbito/exbito-api-docs'>Source Code</a>
includes:
  - publics
  - privates
  - websocket
  - errors
  - limits
  - changelog

search: true

code_clipboard: true

meta:
  - name: description
    content: Documentation for the Exbito API
---

# Introduction

Welcome to the Exbito API! You can use our API to access Exbito API endpoints.

# Authentication

Exbito uses `API_KEY` and `API_SECRET` keys to allow access to the API. You can register a new API key at the [profile settings -> API keys](https://app.exbito.com/more/api).

Exbito expects for the both `API_KEY` and `API_SECRET` to be included in all API requests to the server in a header that looks like the following:

```
X-Api-Key: MY_API_KEY
X-Api-Secret: MY_API_SECRET
```

<aside class="notice">
You must replace <code>MY_API_KEY</code> and <code>MY_API_SECRET</code> with your personal API key and secret.
</aside>

<aside class="notice">
Please NEVER share your API secret with anyone!
</aside>


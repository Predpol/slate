---
title: PredPol API Reference

language_tabs:
  - shell

toc_footers:
  - <a href='https://www.predpol.com/'>PredPol</a>
  - <a href='https://github.com/tripit/slate'>Documentation Powered by Slate</a>

includes:
    - import
    - mission
    - district

search: true
---

# Introduction

Use the APIs described on this page to interact with the Predpol application.

# Authentication

```shell
curl -H "X-Predpol-Key: YOUR_API_KEY"
```

All requests to the Predpol API must include your API key in the header as the `X-Predpol-Key`. 

In order to generate your key
an interface is provided within the application under settings. To create your key login to Predpol with your username and password. Go to `Manage > General` and scroll to the bottom of the page.
Click the red button in the row for `API Key`.

<aside class="warning">
Generating a new API Key will permanently revoke any previously issued key.
</aside>

If you are sure want to generate a new key click `YES` in the confirmation dialog. Your new key is now displayed next to the button, and is immediately available for use.


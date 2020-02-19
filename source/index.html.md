---
title: Solon API

toc_footers:
  - <a href='https://github.com/lord/slate'>Documentation Powered by Slate</a>

includes:
  - proposals
  - votes
  - events
  - attenders
  - forumposts
  - comments
  - users
  - admins
  - statuscodes

search: true
---

# Introduction

Welcome to the Solon API! You can use our API to access Solon API endpoints, which can get information on content in our database.

# Authentication

Solon API expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: apikeyhere`

<aside class="notice">
You must replace <code>apikeyhere</code> with your personal API key.
</aside>
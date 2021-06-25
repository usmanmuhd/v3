+++
title = "GSoC Coding Period Update 2"
date = 2019-06-20T08:35:43+05:30
draft = false
tags = ["gsoc2019", "opensource"]
categories = ["Google Summer of Code 2019"]
+++

I started working on the [second issue](https://phabricator.wikimedia.org/T215222). The **Recommendation API translation endpoint** used to fail
intermittently. After investigating the issue, the point where the bug was being caused was found. The internal request being made to the MediaWiki API was
returning a server error due to issues with the API (Russian MediaWiki API in our case). It was requesting 500 items at once.
To overcome the issue I split the request being into batches of 50 at a time. Each response is then checked if it has an internal server error
and then that response is not considered.

After doing this I ran into errors with Wikidata Query Service. It was taking a lot of time to respond to the query when 500 items were passed at once.
Here also the query was split into 50 items at a time.

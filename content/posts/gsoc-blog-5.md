+++
title = "GSoC Coding Period Update 3"
date = 2019-07-18T08:35:43+05:30
draft = false
tags = ["gsoc2019", "opensource"]
categories = ["Google Summer of Code 2019"]
+++

I am working on the [third issue](https://phabricator.wikimedia.org/T216750). In the  translation end point of the Recommendation API,
currently we fetch the wikidata_id from the respective wikipedia API and then we have a SparQL query that gets the data about the sitelink_counts and removes the
disambiguation pages.

I have pushed a [patch](https://gerrit.wikimedia.org/r/#/c/523779/) to get all the data in a single request from the respective wikipedia API.
This removes the dependency on Wikidata Query Service and ensures that the API responds faster.
Also after the previous patch the API was returning a 429 error as WDQS was blocking our requests which had been split into batches of 50.
This patch solves that issue as well.

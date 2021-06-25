+++
title = "GSoC Second Evaluation"
date = 2019-07-29T18:40:58+05:30
draft = false
tags = ["gsoc2019", "opensource"]
categories = ["Google Summer of Code 2019"]
+++


## Second Evaluation Summary:

#### Issue being worked upon:
- [**T216750: Article recommendation API: replace WDQS with MW API**](https://phabricator.wikimedia.org/T216750)

The WDQS dependency has finally been removed fully. The method being followed is:

1. Get the langlinks and langlinkscount from props.
2. Get ppprop if the page is diambiguation.
3. Consider the wikidata item if it is not in the lang and is not disambiguation.
4. Convert the data into required format for returning

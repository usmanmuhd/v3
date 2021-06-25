+++
title = "GSoC Coding Period Update 4"
date = 2019-08-12T18:40:58+05:30
draft = false
tags = ["gsoc2019", "opensource"]
categories = ["Google Summer of Code 2019"]
+++

I started working on the [4th issue (Bulk import data to MySQL in chunks)](https://phabricator.wikimedia.org/T211980).

The flow of importing the tsv file to the database is:

1. Generate the folder name, delete the folder if it exists and create a new one.
2. Split the tsv file into chunks and place it in the folder.
3. Insert the chunks one at a time.
4. If the import fails at any given chunk then rollback the execution to a previous stable state.
5. Commit the transaction.

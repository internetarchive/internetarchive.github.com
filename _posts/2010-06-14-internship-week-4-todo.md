---
layout: post
title: Internship - Week 4 Todo
categories:
- intern
- bookserver
---

This week, Daniel work on writing a bot for Open Library, using the skills he
learned while creating [the roboblogger](http://github.com/dmontalvo/roboblogger).
This bot will load identifiers from a CSV file into Open Library edition records.

Here is the plan of attack for week 4:

* Get an Open Library instance up an running in a VirtualBox VM
    * [Setup docs](http://openlibrary.org/dev/docs/setup)
* Load a few sample books into the dev instance
    * You can use `./scripts/copydocs.py /books/olid --recursive` to load a single book
* Create a two-column csv file with dummy identifers
    * Column 1 is Amazon IDs
    * Column 2 is OL edition ids (using the sample ids from above step)
    * Get CSV file of real IDs from george to look at
    * Use [python library](http://docs.python.org/library/csv.html) for dealing with csv files
* Create a user named IdentifierBot in your dev instance and add this user to the API group
* Write a python script that loops over the CSV file and adds the identifiers to OL edition records
    * Use the [OpenLibrary python api](http://openlibrary.org/dev/docs/bots) to interact with OL
    * Use a sqlite file to keep state, so you can restart the bot if it dies at some point
    * Gracefully handle conflicts in case that an edition record already contains a different Amazon ID
        * Talk to George or Edward about how to deal with conflicting IDs
* When it works, use the bot to write new IDs into the live site
    * Get CSV of real IDs from george

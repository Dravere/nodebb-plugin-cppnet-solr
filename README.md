# Solr Search for NodeBB

**This is a fork of the original nodebb-plugin-solr package. It includes some minor adjustments that are pushed upstream.**

[From Wikipedia](http://en.wikipedia.org/wiki/Apache_Solr):
> Solr (pronounced "solar") is an open source enterprise search platform from the Apache Lucene project. Its major features include full-text search, hit highlighting, faceted search, dynamic clustering, database integration, and rich document (e.g., Word, PDF) handling.

This plugin extends NodeBB to utilise an installation of Apache Solr as a search backend.

## Configuration

1. Install this plugin via npm: `npm install nodebb-plugin-cppnet-solr`
1. Activate it in the Plugins page
1. Restart NodeBB
1. Check that the plugin has successfully connected to the search engine. If not, adjust as necessary.

## Installation

    npm install nodebb-plugin-cppnet-solr

## Adjustments

The list of differences from the nodebb-plugin-solr version 5.0.0:

* Rebuilding dialog is displayed when the user navigates back to the plugin page and the rebuilding is still going on
* Removed unnecessary retrieval of all user entries in the database (no index is built from it anyway)
* Batching of topic metadata collection (can fix timeout issues with the MongoDB)
* Updated LRU-cache and solr-client dependencies to latest versions
* Removed an error in case of an error (it tried to add to Solr after an error)
* Improved progress reporting (added message what it is doing currently)
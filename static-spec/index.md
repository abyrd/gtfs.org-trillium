---
layout: default
---
# Changing the GTFS Static Spec

### Overview

The official specification exists at [github.com/google/transit](https://github.com/google/transit).

The GTFS Specification is not set in stone. Instead, it is an open specification developed and maintained by the community of transit agencies, developers, and other stakeholders who use GTFS. It is expected that this community of producers and consumers of GTFS data will have proposals for extending the spec to enable new capabilities. To help manage that process, the following procedures and guidelines have been established.

The amendment process is described at [github.com/google/transit/blob/master/gtfs/CHANGES.md](https://github.com/google/transit/blob/master/gtfs/CHANGES.md).

### Guiding Principles
In order to preserve the original vision of GTFS, a number of guiding principles have been established to take into consideration when extending the spec:

> Feeds should be easy to create and edit.

We chose CSV as the basis for the specification because it's easy to view and edit using spreadsheet programs and text editors, which is helpful for smaller agencies. It's also straightforward to generate from most programming languages and databases, which is good for publishers of larger feeds.

> Feeds should be easy to parse.

Feed readers should be able to extract the information they're looking for with as little work as possible. Changes and additions to the feed should be as broadly useful as possible, to minimize the number of code paths that readers of the feed need to implement. (However, making creation easier should be given precedence, since there will ultimately be more feed publishers than feed readers.)

> Changes to the spec should be backwards-compatible.

When adding features to the specification, we want to avoid making changes that will make existing feeds invalid. We don't want to create more work for existing feed publishers until they want to add capabilities to their feeds. Also, whenever possible, we want existing parsers to be able to continue to read the older parts of newer feeds.
Speculative features are discouraged.

Every new feature adds complexity to the creation and reading of feeds. Therefore, we want to take care to only add features that we know to be useful. Ideally, any proposal will have been tested by generating data for a real transit system that uses the new feature and writing software to read and display it. Note that the GTFS readily allows for extensions to the format through the addition of extra columns and files that are ignored by the official parsers & validators, so proposals can be easily prototyped and tested on existing feeds.

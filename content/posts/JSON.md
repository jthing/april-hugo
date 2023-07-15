---
title: "JSON Reader"
date: 2023-07-15T00:00:00+02:00
draft: false
---

## JSON reader for Vulcan {#json-reader-for-vulcan}

There are numerous JSON readers in Common Lisp.
See [JSON review](<https://sabracrolleton.github.io/json-review.html#standard-conformity>).
I don't like any of them. They are over-complicated and translate into a binary lisp
format that is hard to read and debug without using the inspector.
A JSON file can all be read with plist's and lists.

There are numerous options and steps involved in setting up a Vulcan pipeline. They
involve setting at on of &lt;something&gt;Info structures and then calling the functions. The
sequence is deterministic across different pipe setting. My idea is to set it up in the same
way as cascading style sheets. Set up a YAML file with the settings for a generic compute
pipeline. Convert it to JSON. Then convert it to plist format. For each &lt;something&gt;Info
structure you need to set look it up and use the values from the plist.

The idea of the cascade is that you only need to specific the values that differ from the
default. If you prefer plist of JSON format that is fine too just check the file extension.

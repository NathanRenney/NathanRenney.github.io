+++
draft = true
+++

# Notes on how this site works

## Templates

The Zoal templates here are setup such that:

Index is the base template which provides the home page body.

This body is overridden by base which is then further extended based on whether we are at a section or a page.
Sections are created when an _index.md is present in a subdir and provides a title.

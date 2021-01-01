# Overview

Brain is a very simple CLI tool to store text for later retrieval.

# Installation

`cp brain search ~/bin`

# Saving stuff to the brain

```
brain This line I want to store in the brain
brain This will store some optional tags #example #tags
cat FILE | brain #more #optional #tags
```

# Finding stuff in the brain

There's a simple `search` tool which will find tagged files for you.

Find all files with tags 'example' AND 'tags':

```
search example tags
```

You can do OR logic as well, since `search` is using egrep:

```
search 'example|banana' tags
```

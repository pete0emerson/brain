# Overview

Brain is a very simple CLI tool to store text for later retrieval.

# Installation

`cp brain search ~/bin`

# Saving stuff to the brain

```
brain This line I want to store in the brain
echo "Save this stuff to the brain" | brain
cat FILE | brain
```

The file will be saved in ~/brain/${date}/${time}. If there is text on the first line,
that will be saved in the filename after the time, as well.

# Finding stuff in the brain

There's a simple `search` tool which will help find files for you.

Find all files with 'example' AND 'tags':

```
search example tags
```

You can do OR logic as well, since `search` is using egrep:

```
search 'example|banana' tags
```

# Overview

Brain is a very simple CLI tool to store text for later retrieval.

# Installation

Copy `brain`somewhere in your `PATH`.

`cp brain ~/bin`

# Examples of saving text to the brain

```
$ brain This line I want to store in the brain
$ echo "Save this stuff to the brain" | brain
$ cat FILE | brain
```

# Help

```
$ brain -h
Usage: ./brain [ -i -e ] [ -s [-f -r -t TIME]] PATTERN
   -h Show help
   -d Turn on debug mode

	Creation flags

   -e Use an $EDITOR (can be combined with interactive mode)
   -i Interactive mode

	Document search mode (-s)

   -s Use search mode instead of creation mode
   -f Show the full document(s) instead of just the first line
   		(search still matches the first line only)
   -r Reverse the output (newest entries on bottom)
   -t TIME	Specify a time to search back to (10m, 1h, 1d, 7d)
   		defaults to '1d'
```

The file will be saved in ~/brain/${date}/${time}. If there is text on the first line,
that will be saved in the filename after the time, as well.

# Finding stuff in the brain

Adding the `-s` flag to brain will help find content for you.

Find all files with 'example' AND 'tags':

```
brain -s example tags
```

You can do OR logic as well, since `search` is using egrep:

```
brain -s 'example|banana' tags
```

You can also limit your search by time:

```
brain -s -t 1d 'example|banana' tags
```

# Advanced

I'm using [iTerm2](https://iterm2.com/), and I have a Hotkey set up to run a "brain" profile and it executes `brain -e && exit`.
In doing this, I press `Ctrl-Space`, and a window pops up, I type what I want to capture, and it closes
the window for me automatically.

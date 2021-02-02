# Overview

Brain is a very simple CLI tool to store text for later retrieval.

# Installation

Copy `brain` and `search` somewhere in your `PATH`.

`cp brain search ~/bin`

# Examples of saving text to the brain

```
$ brain This line I want to store in the brain
$ echo "Save this stuff to the brain" | brain
$ cat FILE | brain
```

# Help

```
$ brain -h
Usage: /Users/pete/bin/brain [ -i ] [ -s ] [ -e ]
   -e Use an $EDITOR (can be combined with interactive or single line mode)
   -i Interactive mode
   -s Single line interactive mode

$ search -h
Usage: /Users/pete/bin/search [ -t TIME ] [ PATTERN ]
   -f       Show the full document instead of just the first line
   -t TIME	Specify a time to search back to (1h, 1d, 7d)
```

The file will be saved in ~/brain/${date}/${time}. If there is text on the first line,
that will be saved in the filename after the time, as well.

# Finding stuff in the brain

There's a simple `search` tool which will help find content for you.

Find all files with 'example' AND 'tags':

```
search example tags
```

You can do OR logic as well, since `search` is using egrep:

```
search 'example|banana' tags
```

You can also limit your search by time:

```
search -t 1d 'example|banana' tags
```

# Advanced

I'm using [iTerm2](https://iterm2.com/), and I have a Hotkey set up to run a "brain" profile and it executes `brain -e && exit`.
In doing this, I press `Ctrl-Space` or double-tap `Ctrl`, and a window pops up, I type what I want to capture, and it closes
the window for me automatically.

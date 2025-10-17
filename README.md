# Forklift

A shell script to ease the cognitive load of working with agentic CLI tools.

## Installation
You can use `curl` to install Forklift from GitHub. Make sure to install the
script to a location on the `PATH`!

``` sh
# curl ...
# chmod +x
```

## Usage
The best way to use Forklift is by setting up a `tmux` keybinding to open in a
new window. I use `<tmux-leader>i` like so:

``` tmux
bind-key -r i run-shell "tmux neww forklift"
```

You can also run Forklift from the shell:
``` sh
forklift [<branch-name>]
```

## The problem

While agentic CLI tools can be very helpful for some tasks, there is a
significant cost associated with them in that they *take the developer's focus
away from the code*. When using an AI CLI tool, the developer usually needs to
babysit the agent by confirming the tools it should be allowed to use, whilst
also pausing their own work on the code so they don't step on the agent's
robotic toes.

## The solution

Forklift works by asking the user once for a task, then setting the agent to
work with free reign over a separate, dedicated [Git
worktree](https://git-scm.com/docs/git-worktree). When the agent finishes
working the worktree is deleted, leaving the user free to inspect the changes,
e.g. using `git diff`.



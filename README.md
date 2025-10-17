# Forklift

A shell script to ease the cognitive load of working with agentic CLI tools.

> [!NOTE]
> Currently only supports the Copilot CLI.

![Demo](https://github.com/user-attachments/assets/b8bedb2d-8949-4455-b6bc-981f9f4fa8b0)

## Installation
You can use `curl` to install Forklift from GitHub. Make sure to install the
script to a location on the `PATH`!

``` sh
curl https://raw.githubusercontent.com/wurli/forklift/refs/heads/main/forklift -o "$HOME/.local/bin/forklift"
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
away from the code*. The developer usually needs to invest significant time and
attention, first to babysit the agent while it runs, then to clean up the
project when it's finished.

## The solution

Forklift works by asking the user once for a task, then setting the agent to
work with free reign over a separate, dedicated [Git
worktree](https://git-scm.com/docs/git-worktree). When the agent finishes
working the worktree is deleted, leaving the user free to inspect the changes,
e.g. using `git diff`.

## Disclaimer

Forklift currently gives the agent free-reign over its worktree, but does
**not** provide any guardrails beyond instructions in the initial prompt to
stop it changing other files or Git branches. Please only trust Forklift to the
extent that you trust the agent!

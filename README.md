# 🛠️ Forklift 🛠️

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

## Why Use Forklift?

Until I came up with this workflow I found there was usually too much mental
overhead associated with AI coding for me to want to use it. Forklift solves
these problems:

-   I don't have to babysit the agent while it works
-   I don't have to clean up after it
-   Once I'm done writing the prompt I can _immediately_ get back to what I was
    doing
-   I'm free to review the AI's work in my own time using Git

## Disclaimer

Forklift currently gives the agent free-reign over its worktree, but does
**not** provide any guardrails beyond instructions in the initial prompt to
stop it changing other files or Git branches. Please only trust Forklift to the
extent that you trust the agent!

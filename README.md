# telescope-git-submodule.nvim

A customizable telescope extension to list the git submodules of your current project and interact with them through the git TUI of your choice.

## Installation

Using lazy.nvim in lua

```lua
{
    "nvim-telescope/telescope.nvim",
    dependencies = {
        "agoodshort/telescope-git-submodules.nvim",
    },
    config = function()
        require("telescope").load_extension("git_submodules")
    end,
}
```

## Features

- List the git submodules of the currently opened project
- Preview the changes for each submodule directly in telescope
- Use the terminal plugin of your choice
- Run the git TUI (or command) of your choice when selecting a submodule in telescope
- Bypass telescope if only one repo/submodule should be displayed

## Acknowledgements

Inspired by [lazygit.nvim](https://github.com/kdheepak/lazygit.nvim)

# telescope-git-submodules.nvim

A customizable Telescope extension to list the git submodules of your current project and interact with them through the git TUI of your choice.

<https://github.com/agoodshort/telescope-git-submodules.nvim/assets/33832653/5d13113f-16a2-40f7-91e4-816827234240>

## Features

- List the git submodules of the currently opened project
- Preview the files changes for each submodule directly in Telescope
- Run the git TUI (or command) of your choice when selecting a submodule in Telescope
- Bypass Telescope if only one repo/submodule would be displayed in Telescope

## Installation

Using [lazy.nvim](https://github.com/folke/lazy.nvim)

```lua
return {
	"nvim-telescope/telescope.nvim",
	dependencies = {
		{
			"agoodshort/telescope-git-submodules.nvim",
			dependencies = "akinsho/toggleterm.nvim",
		},
	},
	config = function()
		require("telescope").load_extension("git_submodules")
	end,
}
```

## Configuration

The extension comes with the following defaults:

```lua
require("telescope").setup({
	extensions = {
		git_submodules = {
			git_cmd = "lazygit",
			terminal_id = 9,
		},
	},
})
```

### Extension Specs

| Property    | Type    | Default Value | Description                      |
|-------------|---------|---------------|----------------------------------|
| git_cmd     | string? | "lazygit"     | git TUI command of your choice   |
| terminal_id | number? | 9             | Terminal ID toggleterm will use  |

## Roadmap

- [ ] Keymap to trigger `:DiffView` for the highlighted submodule
- [ ] Support additional terminal plugins (e.g., [nvim-terminal](https://github.com/s1n7ax/nvim-terminal))

## Acknowledgements

Inspired by [lazygit.nvim](https://github.com/kdheepak/lazygit.nvim)

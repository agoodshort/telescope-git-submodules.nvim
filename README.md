# telescope-git-submodule.nvim

A customizable telescope extension to list the git submodules of your current project and interact with them through the git TUI of your choice.

## Features

- List the git submodules of the currently opened project
- Preview the changes for each submodule directly in telescope
- Run the git TUI (or command) of your choice when selecting a submodule in telescope
- Bypass telescope if only one repo/submodule should be displayed

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

```lua
  require("telescope").setup({
  	extensions = {
  		git_submodules = {
  			git_cmd = "lazygit",
  			terminal_count = 9,
  		},
  	},
  })
```

## Roadmap

- [ ] Use the terminal plugin of your choice
- [ ] Keymap to trigger `:DiffView` for the highlighted submodule

## Acknowledgements

Inspired by [lazygit.nvim](https://github.com/kdheepak/lazygit.nvim)

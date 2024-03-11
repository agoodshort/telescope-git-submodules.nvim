# telescope-git-submodules.nvim

A customizable [telescope.nvim extension](https://github.com/nvim-telescope/telescope.nvim#extensions) to list the git submodules of your current project and interact with them through the git TUI of your choice.

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
			previewer = true,
			terminal_id = 9,
			diffview_keymap = "<C-d>",
		},
	},
})
```

### Extension Specs

| Property        | Type     | Default Value | Description                                                     |
|-----------------|----------|---------------|-----------------------------------------------------------------|
| git_cmd         | string?  | "lazygit"     | git TUI command of your choice                                  |
| previewer       | boolean? | true          | Preview submodule changes in Telescope                          |
| terminal_id     | number?  | 9             | Terminal ID toggleterm will use                                 |
| diffview_keymap | string?  | "<C-d>"       | Keymap to trigger `:diffviewOpen` for the highlighted submodule |

## Plugin integration

### nvim-unception

The extension integrates pretty well (at least from my personal experience) with [nvim-unception](https://github.com/samjwill/nvim-unception), if the same `terminal_id` value is used in both configurations. Example in [agoodshort's nvim-unception configuration](https://github.com/agoodshort/nvim/blob/e9e89782e124e3c666097edeb0603317b8e72320/lua/agoodshort/plugins/terminal/nvim-unception.lua#L11)

### diffview.nvim

If you have [diffview.nvim](https://github.com/sindrets/diffview.nvim), you can use the `diffview_keymap` to trigger `:diffviewOpen -C<path>` for the highlighted submodule.

## Roadmap

- [ ] Support additional terminal plugins (e.g., [nvim-terminal](https://github.com/s1n7ax/nvim-terminal))
- [ ] Add the option to point `:diffviewOpen` to `origin/HEAD`

## Acknowledgements

Inspired by [lazygit.nvim](https://github.com/kdheepak/lazygit.nvim)

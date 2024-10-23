# jsonpath.nvim

Do you often find yourself in large JSON files needing to know the path of
the element your cursor is on? jsonpath.nvim is a minimal Neovim plugin that
does exactly that - it shows you the JSON path of the current element under
your cursor.

While not perfect, it serves it's purpose.

## Features

- Shows JSON path of the current element under cursor
- Follows `jq`-compatible syntax
- Yank JSON path

## Requirements

- Neovim
- [nvim-treesitter](https://github.com/nvim-treesitter/nvim-treesitter)

## Installation

Using [lazy.nvim](https://github.com/folke/lazy.nvim):

```lua
return {
  "philippdrebes/jsonpath.nvim",
  dependencies = { "nvim-treesitter/nvim-treesitter" },
  config = function()
    local jsonpath = require("jsonpath")
      jsonpath.setup()
      vim.keymap.set("n", "<leader>jp", function() jsonpath.show_json_path() end, { desc = "Show JSON Path" })
      vim.keymap.set("n", "<leader>jpy", function() jsonpath.yank_json_path() end, { desc = "Yank JSON Path" })
  end,
}
```

## Usage

1. Place your cursor on any element in a JSON file
2. Press `<leader>jp` to show the JSON path
3. Press `<leader>jpy` to yank the JSON path

## Example

![./screenshot.png](./screenshot.png)

## Contributing

This is a simple plugin that serves a specific purpose. If you find bugs or
have suggestions for improvements that maintain its simplicity, feel free to
open an issue or submit a pull request.

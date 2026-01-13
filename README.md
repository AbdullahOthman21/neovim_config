# My neovim 0.12 config ._.

```lua
vim.o.termguicolors = true
vim.o.clipboard = "unnamedplus"
vim.o.mouse = ""
vim.o.splitright = true
vim.o.splitbelow = true
vim.o.smartindent = true
vim.o.signcolumn = "yes:1"
vim.o.tabstop = 4
vim.o.shiftwidth = 4
vim.o.cursorline = true
vim.o.wrap = false
vim.o.sidescrolloff = 4
vim.o.list = true
vim.opt.listchars = { tab = '» ', trail = '·', nbsp = '␣' }
vim.opt.winborder = "rounded"

vim.pack.add({
	{ src = "https://github.com/folke/tokyonight.nvim"},
	{ src = "https://github.com/stevearc/oil.nvim"},
	{ src = "https://github.com/nvim-tree/nvim-web-devicons"},
	{ src = "https://github.com/neovim/nvim-lspconfig" },
	{ src = "https://github.com/nvim-treesitter/nvim-treesitter" },
	{ src = "https://github.com/mason-org/mason.nvim" },
	{ src = "https://github.com/mason-org/mason-lspconfig.nvim" },
	{ src = "https://github.com/nvim-lualine/lualine.nvim" },
	{ src = "https://github.com/folke/which-key.nvim" },
	{ src = "https://github.com/lewis6991/gitsigns.nvim" },
	--{ src = "" },
})
vim.cmd("colo tokyonight")
require("mason").setup()
require("mason-lspconfig").setup()
require("oil").setup({default_file_explorer=true,columns={"icon"},buf_options={buflisted=false,bufhidden="hide"},win_options={wrap=false,signcolumn="no",cursorcolumn=false,foldcolumn="0",spell=false,list=false,conceallevel=3,concealcursor="nvic"},delete_to_trash=false,skip_confirm_for_simple_edits=false,prompt_save_on_select_new_entry=true,cleanup_delay_ms=2000,lsp_file_methods={enabled=true,timeout_ms=1000,autosave_changes=false},constrain_cursor="editable",watch_for_changes=false,keymaps={["g?"]={"actions.show_help",mode="n"},["<CR>"]="actions.select",["<C-s>"]={"actions.select",opts={vertical=true}},["<C-h>"]={"actions.select",opts={horizontal=true}},["<C-t>"]={"actions.select",opts={tab=true}},["<C-p>"]="actions.preview",["<C-c>"]={"actions.close",mode="n"},["<C-l>"]="actions.refresh",["-"]={"actions.parent",mode="n"},["_"]={"actions.open_cwd",mode="n"},["`"]={"actions.cd",mode="n"},["g~"]={"actions.cd",opts={scope="tab"},mode="n"},["gs"]={"actions.change_sort",mode="n"},["gx"]="actions.open_external",["g."]={"actions.toggle_hidden",mode="n"},["g\\"]={"actions.toggle_trash",mode="n"}},use_default_keymaps=true,view_options={show_hidden=false,is_hidden_file=function(a,b)local c=a:match("^%.")return c~=nil end,is_always_hidden=function(a,b)return false end,natural_order="fast",case_insensitive=false,sort={{"type","asc"},{"name","asc"}},highlight_filename=function(d,e,f,g)return nil end},extra_scp_args={},extra_s3_args={},git={add=function(h)return false end,mv=function(i,j)return false end,rm=function(h)return false end},float={padding=2,max_width=0,max_height=0,border=nil,win_options={winblend=0},get_win_title=nil,preview_split="auto",override=function(k)return k end},preview_win={update_on_cursor_moved=true,preview_method="fast_scratch",disable_preview=function(l)return false end,win_options={}},confirmation={max_width=0.9,min_width={40,0.4},width=nil,max_height=0.9,min_height={5,0.1},height=nil,border=nil,win_options={winblend=0}},progress={max_width=0.9,min_width={40,0.4},width=nil,max_height={10,0.9},min_height={5,0.1},height=nil,border=nil,minimized_border="none",win_options={winblend=0}},ssh={border=nil},keymaps_help={border=nil}})
require('lualine').setup()
require('gitsigns').setup()
-------------------------------------------
vim.g.mapleader = " "
vim.keymap.set('n', '<leader>w', ':write<CR>', { noremap = true, silent = true })
vim.keymap.set('n', '<leader>r', ':source<CR>', { noremap = true, silent = true })
vim.keymap.set("n", "Q", "<CMD>Oil<CR>" )
vim.keymap.set("n", "<leader>e", "<CMD>Oil<CR>" )
vim.keymap.set("n", "<leader>d", function() vim.diagnostic.open_float(0, { scope = "line" }) end)
```

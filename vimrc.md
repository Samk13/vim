#My .vimrc settings

```vim

"Install Plugins =========================================
call plug#begin('~/.vim/plugged')

"Git  ====
Plug 'https://github.com/tpope/vim-fugitive.git'
"vim tools
Plug 'itchyny/lightline.vim'

"Syntax highlightighting ====
Plug 'neoclide/coc.nvim', {'branch': 'release'}
Plug 'pangloss/vim-javascript'
Plug 'posva/vim-vue'
Plug 'jwalton512/vim-blade'

"Themes ====
Plug 'morhetz/gruvbox'
Plug 'junegunn/goyo.vim'
call plug#end()
"end install Plugins =====================================


"Themes   ================================================
set guifont=Fira\ Code:h20
"set colorcolumn=90
"highlight colorcolumn ctermbg=0 guibg=lightgrey
set background=dark

colorscheme gruvbox

"end themes ==============================================
"Vim sets ================================================

" activates filetype detection
filetype plugin indent on

" activates syntax highlighting among other things
syntax on

"turn off error bells sound
set noerrorbells

set shiftwidth=2
set smartindent
set nowrap
set noswapfile
set nobackup
set undodir=~/.vim/undodir
set undofile
set incsearch
"set line number
set number

"Vim sets    ================================================
"Keybindings  ===============================================
" auto close brackets
inoremap " ""<left>
inoremap ' ''<left>
inoremap ( ()<left>
inoremap [ []<left>
inoremap { {}<left>
inoremap {<cr> {<cr>}<esc>o
inoremap {;<cr> {<cr>};<esc>o
nnoremap <c-p> :files<cr>
"Keybindings ================================================
"Plugins section ============================================
"FZF
set rtp+=/usr/local/opt/fzf

"lightLine

set laststatus=2
set t_Co=256
set background=dark

"end Plugins section ========================================

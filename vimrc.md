#My .vimrc settings

```vim
if empty(glob('~/.vim/autoload/plug.vim'))
  silent !curl -flo ~/.vim/autoload/plug.vim --create-dirs
    \ https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
  autocmd vimenter * pluginstall --sync | source $myvimrc
endif

" plugins will be downloaded under the specified directory.
call plug#begin('~/.vim/plugged')

" declare the list of plugins.
plug 'ycm-core/youcompleteme'
""plug 'tpope/vim-sensible'
""plug 'junegunn/seoul256.vim'
plug 'junegunn/fzf', { 'do': { -> fzf#install() } }
plug 'junegunn/fzf.vim'
""plug 'drewtempelmeyer/palenight.vim'
plug 'pangloss/vim-javascript'
plug 'posva/vim-vue'
plug 'https://github.com/tpope/vim-fugitive.git'
plug 'itchyny/lightline.vim'
plug 'neoclide/coc.nvim', {'branch': 'release'}
plug 'jwalton512/vim-blade'

plug 'morhetz/gruvbox'
plug 'junegunn/goyo.vim'
" list ends here. plugins become visible to vim after this call.
call plug#end()

"themes ================================================
"set background=dark
""colorscheme palenight
"font and size
set guifont=menlo-regular:h19
set colorcolumn=90
highlight colorcolumn ctermbg=0 guibg=lightgrey
colorscheme gruvbox
set background=dark

"end themes ================================================


"vim-javascript
let g:javascript_plugin_jsdoc = 1


"smooth scrolling comfortable-motion
let g:comfortable_motion_scroll_down_key = "j"
let g:comfortable_motion_scroll_up_key = "k"


"fzf

" for faster search
if executable('rg')
    let g:rg_derive_root='true'
endif



set rtp+=/usr/local/opt/fzf
" this is the default extra key bindings
let g:fzf_action = {
  \ 'ctrl-t': 'tab split',
  \ 'ctrl-x': 'split',
  \ 'ctrl-v': 'vsplit' }
" default fzf layout
" - down / up / left / right
let g:fzf_layout = { 'down': '~60%' }

" you can set up fzf window using a vim command (neovim or latest vim 8 required)
let g:fzf_layout = { 'window': 'enew' }
let g:fzf_layout = { 'window': '-tabnew' }
let g:fzf_layout = { 'window': '20new' }

" customize fzf colors to match your color scheme
" - fzf#wrap translates this to a set of `--color` options
let g:fzf_colors =
\ { 'fg':      ['fg', 'normal'],
  \ 'bg':      ['bg', 'normal'],
  \ 'hl':      ['fg', 'comment'],
  \ 'fg+':     ['fg', 'cursorline', 'cursorcolumn', 'normal'],
  \ 'bg+':     ['bg', 'cursorline', 'cursorcolumn'],
  \ 'hl+':     ['fg', 'statement'],
  \ 'info':    ['fg', 'preproc'],
  \ 'border':  ['fg', 'ignore'],
  \ 'prompt':  ['fg', 'conditional'],
  \ 'pointer': ['fg', 'exception'],
  \ 'marker':  ['fg', 'keyword'],
  \ 'spinner': ['fg', 'label'],
  \ 'header':  ['fg', 'comment'] }


" auto close brackets
inoremap " ""<left>
inoremap ' ''<left>
inoremap ( ()<left>
inoremap [ []<left>
inoremap { {}<left>
inoremap {<cr> {<cr>}<esc>o
inoremap {;<cr> {<cr>};<esc>o
nnoremap <c-p> :files<cr>



" activates filetype detection
filetype plugin indent on

" activates syntax highlighting among other things
syntax on

"turn off error bells sound
set noerrorbells

" shift width
set shiftwidth=2
set smartindent
set nowrap
set noswapfile
set nobackup
set undodir=~/.vim/undodir
set undofile
set incsearch



" set line number
set number


" allows you to deal with multiple unsaved
" buffers simultaneously without resorting
" to misusing tabs
set hidden

" just hit backspace without this one and
" see for yourself
set backspace=indent,eol,start




function! cocbuildupdate()
  if has('nvim')
    " note: setup a `list` in viml to supply the coc `install_extension` func
    " todo: autogen global_extensions in a var, ie. don't hardcode
    let g:coc_global_extensions = [
          \ 'coc-css',
          \ 'coc-html',
          \ 'coc-json',
	  \ 'coc-php',
          \ ]
    call coc#util#install()
    call coc#util#install_extension(g:coc_global_extensions)
  endif
endfunction


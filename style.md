```bash
set nocompatible
 
" Vundle
" """"""""""""""""""""""""""""""""""""""""""""""""""""""""
filetype off
set rtp+=~/.vim/bundle/Vundle.vim
call vundle#begin()
Plugin 'gmarik/vundle'
Plugin 'altercation/vim-colors-solarized'
Plugin 'godlygeek/tabular'
 
" code highlight
Plugin 'plasticboy/vim-markdown'
Plugin 'pangloss/vim-javascript'
Plugin 'mxw/vim-jsx'
Plugin 'dag/vim2hs'
Plugin 'groenewege/vim-less'
 
Plugin 'rstacruz/sparkup'
Plugin 'kien/ctrlp.vim'
Plugin 'Valloric/YouCompleteMe'
Plugin 'tpope/vim-pathogen'
Plugin 'scrooloose/syntastic'
 
Plugin 'bling/vim-airline'
 
Plugin 'tpope/vim-git'
Plugin 'tpope/vim-fugitive'
 
 
call vundle#end()  
filetype plugin indent on
 
" General Config
""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set history=50
set confirm " 沒作用? Ask for comfirmation in some situation(:q)
set ignorecase smartcase " case insensitive search, except when mixing case
set modeline " we allow modelines in textfiles to set vim setting
" allow to change buffer without saving
" 允許在有未保存的修改時切換緩沖區，此時的修改由 vim 負責保存
set hidden 
" set mouse=a " enable mouse in all modes例如滑鼠點選位置,移動位置etc
set noerrorbells "dont make noise
set novisualbell "dont blink
set exrc " Scan working dir for .vimrc
set secure " Make the above safely
set autoread " reload files changed outside vim (待確認)
set nobackup
set noswapfile
set omnifunc=syntaxcomplete#Complete " for autocomplete YCM
set encoding=utf-8
 
" More natural split opening
set splitbelow
set splitright
 
" UI/Colors
""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set guifont=Ubuntu\ Mono\ derivative\ Powerline\ 16
set cursorline " highlight the current line
set wildmenu " Show suggestions on TAB for some commands
set ruler " 好像沒有用?
set cmdheight=1 " the command bar is 1 high 設定命令行行數為1
set number
" make backspace work normal 插入狀態也可以使用backspace和del?
set backspace=indent,eol,start 
set whichwrap+=<,>,h,l " 讓h,l方向鍵到行開頭結尾都可繼續上下一行
set report=0
set laststatus=2 " always show the status line
" set statusline=[%n]\ [%f]\ %w%y%r%m[%{&fileformat}][%{&fileencoding}]\ %=\ %l/%L,%-5c\ %P\
set scrolloff=10 "Start scrolling this number of lines from top/bottom
set incsearch " 邊打搜尋的時候就會邊顯示目前畫面符合的字串Find the next match as we type the search
set hlsearch " 搜尋到的結果高亮顯示 Highlight searches by default
 
set t_Co=256 " Enable 256 color mode
syntax on " syntax highlighting on (set before colorscheme)
syntax enable
colorscheme solarized
set background=dark
 
" Indentation
""""""""""""""""""""""""""""""""""""""""""""""""""""""""
set autoindent
set smartindent
set smarttab
set shiftwidth=2
set softtabstop=2
set tabstop=2
set expandtab
 
" 進insert mode按F2就會到paste mode, 貼上code就不會有額外indenting,
" 貼好後再按F2取消paste mode
" http://nvie.com/posts/how-i-boosted-my-vim/
set pastetoggle=<F2> 
 
" Folding
""""""""""""""""""""""""""""""""""""""""""""""""""""""""
"set fdm=syntax
"set foldnestmax=3
 
" Key Mapping
""""""""""""""""""""""""""""""""""""""""""""""""""""""""
 
" \rr 就可source vimrc!
nnoremap <leader>rr :source ~/.vimrc<cr>
 
" Press Space to turn off highlighting and clear any message already
" displayed. 按空白就取消搜尋結果高亮
nnoremap <silent> <Space> :nohlsearch<Bar>:echo<CR>
 
" 這樣就不用每次還要shift+; --> :w 只要 ;w就可以了
" 不過會衝到;指令(repeat previous command)
nnoremap ; :
 
"Easy split window navigation
map <C-h> <C-w>h
map <C-j> <C-w>j
map <C-k> <C-w>k
map <C-l> <C-w>l
 
 
" Plugin options
""""""""""""""""""""""""""""""""""""""""""""""""""""""""
 
"Solarize theme options
" let g:solarized_termcolors=256
let g:solarized_bold=1 
let g:solarized_underline=1 
let g:solarized_italic=1
let g:solarized_contrast='high'
let g:solarized_termtrans = 1 
 
"Markdown options
let g:vim_markdown_folding_disabled=1 " only control markdown folding
let g:vim_markdown_frontmatter=1 " enable YAML formatter
 
"vim-javascaript options
let javascript_enable_domhtmlcss=1
 
"vim-jsx options
let g:jsx_ext_required=0
 
"vim-powerline options
let g:airline_powerline_fonts = 1
let g:airline_theme = 'solarized'
 
"syntastic options
let g:syntastic_javascript_checkers = ['jsxhint']
```

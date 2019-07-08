# git color
git config --global user.name "Matt Mix"
git config --global user.email "matthew.w.mix@gmail.com"
git config --global core.editor nvim
git config --global color.ui true

# ZSH
dnf install zsh
curl -L http://install.ohmyz.sh | sh

# nvim ~/.config/nvim/init.vim
" nerdtree
map <C-o> :NERDTreeToggle<CR>
autocmd bufenter * if (winnr("$") == 1 && exists("b:NERDTree") && b:NERDTree.isTabTree()) | q | endif
" end nerdtree

" fzf
map ; :FZF<CR>
" end fzf

call plug#begin()
Plug 'junegunn/fzf', { 'dir': '~/.fzf', 'do': './install --all' }
Plug 'w0rp/ale'
Plug 'sheerun/vim-polyglot'
Plug 'scrooloose/nerdtree'
Plug 'itchyny/lightline.vim'
call plug#end()

set number

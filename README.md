# git color
git config --global user.name "Matt Mix"
git config --global user.email "matthew.w.mix@gmail.com"
git config --global core.editor nvim
git config --global color.ui true

# vim-colors-solarized
https://github.com/altercation/vim-colors-solarized

# ZSH
dnf install zsh
curl -L http://install.ohmyz.sh | sh

# Tmux plugin manager
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm

# tmux ~/.tmux.conf
# List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'seebi/tmux-colors-solarized'

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com/user/plugin'
# set -g @plugin 'git@bitbucket.com/user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run -b '~/.tmux/plugins/tpm/tpm'

set -g @colors-solarized 'dark'
set -g default-command /bin/zsh

# install neovim python pip thing
pip3 install --user --upgrade pynvim

# follow instructions
https://github.com/deoplete-plugins/deoplete-go

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
Plug 'micha/vim-colors-solarized'
Plug 'fatih/vim-go', { 'do': ':GoUpdateBinaries' }
Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
Plug 'deoplete-plugins/deoplete-go', { 'do': 'make'}
Plug 'nsf/gocode', { 'rtp': 'nvim', 'do': '~/.config/nvim/plugged/gocode/nvim/symlink.sh' }
call plug#end()

if has('nvim')
    " Enable deoplete on startup
    let g:deoplete#enable_at_startup = 1
    let g:deoplete#sources#go#gocode_binary = "/development/bin/gocode"
endif

" tell it to use an undo file
set undofile
" set a directory to store the undo history
set undodir=/root/.vimundo/
set hidden

set number

syntax enable
set background=dark
colorscheme solarized

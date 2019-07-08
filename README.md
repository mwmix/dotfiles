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

# Other examples:
# set -g @plugin 'github_username/plugin_name'
# set -g @plugin 'git@github.com/user/plugin'
# set -g @plugin 'git@bitbucket.com/user/plugin'

# Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run -b '~/.tmux/plugins/tpm/tpm'

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
call plug#end()

set number

syntax enable
set background=dark
colorscheme solarized

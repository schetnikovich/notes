# Pathogen

Pathogen simplifies installation of Vim plugins.

    $ mkdir -p ~/.vim/autoload ~/.vim/bundle && \
    $ curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim

# vim-sensible 

    $ cd ~/.vim/bundle
    $ git clone git://github.com/tpope/vim-sensible.git

# vim-go

    $ cd ~/.vim/bundle
    $ git clone https://github.com/fatih/vim-go.git

# YouCompleteMe

Make sure that you have this packages installed

    $ sudo apt-get install python-dev
    $ sudo apt-get install build-essential cmake

Install YouCompleteMe:

    $ cd ~/.vim/bundle
    $ git clone https://github.com/Valloric/YouCompleteMe.git
    $ cd YouCompleteMe
    $ git submodule update --init --recursive
    $ ./install.sh

# Markdown syntax highlighting

    $ cd ~/.vim/bundle
    $ git clone https://github.com/plasticboy/vim-markdown.git

# ctrlp.vim

    $ cd ~/.vim/bundle
    $ git clone https://github.com/kien/ctrlp.vim.git

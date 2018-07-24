預設MAC有Python 2.7.10版本 (預設MAC有Python 2.7.10版本)  

[python安裝指南](http://pythonguidecn.readthedocs.io/zh/latest/starting/install3/osx.html)

1. 用Homebrew安裝python3  
```
brew install python
```
> ps:
> * Homebrew會裝好pip3 (pip3是Homebrew版Python3的pip的别名。)  
> * 安裝完後執行python會執行homebrew安裝的python3, python2指令才會執行原本系統的python
> * 可以用python --version / pip --version 確定版本
> * 若預設python還是python2 要加環境變數到PATH
> ```
> export PATH="/usr/local/opt/python/libexec/bin:$PATH"
> ```

2. 安裝Virtual Environment
參考
* [構建Python多個虛擬環境來進行不同版本開發之神器-virtualenv](https://ningyu1.github.io/site/post/63-python-virtualenv/)
* [Virtual Environments Usage](https://python-guide-cn.readthedocs.io/en/latest/dev/virtualenvs.html)

```
pip install virtualenv
virtualenv venv
source ./venv/bin/activate
deactivate
```

3. Neovim
* [deoplete-jedi](https://github.com/zchee/deoplete-jedi)
* pip3 install --user neovim
* 在~/.config/nvim底下touch init.vim
```
" Plugins will be downloaded under the specified directory.
call plug#begin()

"Declare the list of plugins.
Plug 'Shougo/deoplete.nvim', { 'do': ':UpdateRemotePlugins' }
Plug 'zchee/deoplete-jedi'

" List ends here. Plugins become visible to Vimd after this call.
call plug#end()

set runtimepath+=$XDG_CONFIG_HOME/nvim/plugged/deoplete.nvim
set completeopt+=noinsert,noselect
set completeopt-=preview
let g:deoplete#enable_at_startup = 1
filetype plugin indent on

call deoplete#custom#option('num_processes', 1)
```

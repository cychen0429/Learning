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

2. 安裝pipenv (版本管理器 可以讓不同專案使用不同的版本)
```
pip install --user pipenv
```

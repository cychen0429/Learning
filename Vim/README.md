### Tutorial
Use vimtutor in terminal (about 25-30M)
[高見龍 Vim的操作小技巧](https://kaochenlong.com/2011/12/28/vim-tips/)

i insert mode
v virsual mode可以用來選文字 (用y(yank) copy選到的文字 再用p貼上)
o 往下新增一行並進入insert mode
O 往上新增一行並進入insert mode
a 在目前cursor後進入insert mode
A 在行尾進入insert mode
R 進入replace mode
:set ic/noic/hlsearch/nohlsearch

w:下一个词的词首。
e:下一个词的词尾。
b:上一个词的词首。
H、M、L：直接跳转到当前屏幕的顶部、中部、底部。
#H：跳转到当前屏的第#行。
0: 跳转到行首。
$: 跳转到行尾。
zt: 当前编辑行置为屏顶
zz: 当前编辑行置为屏中
zb: 当前编辑行置为屏尾

0表示行頭
$表示行尾
d表示整行
u undo(CTRL+r回復redo, U回覆該line所有動作)

p貼上剛刪除的東西
r是置換字元
ce直接刪到word尾並開啟insert模式(=de+i)
c$直接刪到行尾並開啟insert模式

CTRL+g顯示檔案位置
G to the bottom of the file
gg to the start of the file
500G go to line 500 of the file

/ to search file(往下) ?往上搜尋 (n繼續往下搜尋 N往上收尋)
%找對應的括號( ｜ {

:s/old/new/g (置換該行所有的old變成new)
:5,15s/old/new/g (置換5-15行所有的old變成new)
:%s/old/new/g (置換整個檔案所有的old變成new)
:%s/old/new/gc (置換整個檔案所有的old變成new 每個都跳出確認prompt)

:!執行外部command


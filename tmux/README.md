### Article
[session 管理神器 — tmux](https://larrylu.blog/tmux-33a24e595fbc)  
[影片終端機 session 管理神器 — tmux](https://www.youtube.com/watch?v=nD6g-rM5Bh0&list=PLbkWnfz63JbWlZSq964DCMW64dM06_qht)  
[Tmux Cheet Sheet](http://tmuxcheatsheet.com/)  

### 概念
Session -> Window -> Pane  
用CTRL+b來下指令 
tmux ls來看目前的session/window狀況 
s可以切換不銅的window/pane  

用tmux list-keys來看快速鍵 tmux list-sessions/panes/windows
  
for Pane | []() 
--- | ---
% | 水平分割
" | 垂直分割
方向鍵 | 上下左右移動pane
x | 關閉pane

Window | []()
--- | ---
c | 新增window
p | 切換到上一個window
n | 切換到下一個window
& | 關閉目前window

### Configuration file .tmux.conf under home directory
```
# Send prefix
set-option -g prefix C-b
unbind-key C-b
bind-key C-b send-prefix
 
# Easy config reload
bind-key r source-file ~/.tmux.conf \; display-message "tmux.conf reloaded."
 
# Easy clear history
bind-key L clear-history
  
# Lengthen the amount of time status messages are displayed
set-option -g display-time 2000
set-option -g display-panes-time 3000
  
# Window activity monitor
setw -g monitor-activity on
set -g visual-activity on
 
# Set easier window split keys
bind-key v split-window -h
bind-key h split-window -v
 
# Use Shift-arrow keys without prefix key to switch panes
bind -n S-Left select-pane -L
bind -n S-Right select-pane -R
bind -n S-Up select-pane -U
bind -n S-Down select-pane -D
 
# Allow the arrow key to be used immediately after changing windows.
set-option -g repeat-time 0
 
# Alt arrow to switch windows
bind -n M-Left  previous-window
bind -n M-Right next-window
 
# Window activity monitor
setw -g monitor-activity on
set -g visual-activity on
  
# Mouse Mode
set -g mouse on
 
# Theme
set -g window-status-current-bg green
set -g window-status-current-fg black
set -g window-status-current-attr bold
set-option -g message-bg colour237
set-option -g message-fg colour231
set-option -g pane-border-fg green
set-option -g pane-active-border-fg green
 
# Status Bar
set -g status-justify centre
set -g status-bg black
set -g status-fg white
set -g status-interval 60
set -g status-left-length 30
set -g status-left '#[fg=green][#S] #(whoami)@#H'
set -g status-right '#[fg=green]#(cut -d " " -f 1-3 /proc/loadavg)#[default]  #[fg=green]%H:%M'
```

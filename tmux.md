# tmux

```
# 新建
tmux
tmux new -s <session-name>

# 退出
exit
ctrl+d

# 分离
tmux detach
ctrl+b d

#查看
tmux ls
#接入
tmux attach -t
# 杀死
tmux kill-session -t <session-name/number>

#
ctrl+b p/n

# 划分窗格，左右
tmux split-window -h
```

## Tmux cheatsheet

prefix: ctrl-b

`tmux new -s session_name`
`tmux attach -t session_name` attach to the current running session
if there is only one session running, just do `tmux a`
`tmux list-sessions` list sessions


###### commands: 
* `prefix + d` detach current tmux session
* `prefix + %` split horizontally
* `prefix + "` split vertically
* `prefix + UP/DOWN/LEFT/RIGHT` go to differet panes
* `prefix + c` create new window
* `prefix + n/prefix + p` go to next/previous window
* `prefix + [0-9]` go to the window number 0-9
* `prefix + x` kill current pane
* `prefix + &` kill current window


#### ~/.tmux.conf
<pre>
set status-utf8 on

set -g default-terminal "screen-256color"
set-option -g pane-active-border-fg blue
set -g mode-mouse on
set -g mouse-resize-pane on
set -g mouse-select-pane on
set -g mouse-select-window on

set -g status-bg colour24
set -g status-fg white
set -g window-status-current-bg white
set -g window-status-current-fg colour24
set -g window-status-current-attr bold
</pre>


<hr />
#### Tmuxinator
######very useful tool for managing projects!!

[Github](https://github.com/tmuxinator/tmuxinator)

##### Reloading rbenv in case it doesn't work in tmux
<pre>
# Mac OS X uses path_helper to preload PATH, clear it out first
if [ -x /usr/libexec/path_helper ]; then
    PATH=''
    eval `/usr/libexec/path_helper -s`
fi

# if rbenv is present, configure it for use
if which rbenv &> /dev/null; then
    # Put the rbenv entry at the front of the line
    export PATH="$HOME/.rbenv/bin:$PATH"

    # enable shims and auto-completion
    eval "$(rbenv init -)"
fi
</pre>

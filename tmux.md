# tmux Commands summary
## Summary of Primary Commands

Start new named session:

tmux new -s [session name]
Detach from session:

ctrl+b d
List sessions:

tmux ls
Attach to named session:

tmux a -t [name of session]
Kill named session:

tmux kill-session -t [name of session]
Split panes horizontally:

ctrl+b "
Split panes vertically:

ctrl+b %
Kill current pane:

ctrl+b x
Move to another pane:

ctrl+b [arrow key]
Kill tmux server, along with all sessions:

tmux kill-server

Reference - https://hackernoon.com/a-gentle-introduction-to-tmux-8d784c404340


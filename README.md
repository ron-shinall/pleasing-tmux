# pleasing-tmux
A clean tmux layout that doesn't require any plugins. If you want the CPU & memory status you will need a plugin for that, but it's purely optional.

 <img width="1327" height="779" alt="pleasing_tmux" src="https://github.com/user-attachments/assets/e1b8b0f0-56cf-4e92-8e32-e895513f7f15" />

## Requirements
- A patched [Nerd Font](https://www.nerdfonts.com/)

## Configuration
Copy the contents of `tmux/tmux.conf` to your setup And reload your tmux configuration.

## Troubleshooting
- If colors don't look right you may need these lines in your config:
```sh
set -g default-terminal "screen-256color"
set -ga terminal-overrides ",*256col*:Tc"
```
- If you decide to use the CPU & memory plugin, and you don't see the values in the status bar, check the order of your plugins. For example, this order works for me:
```sh
set -g @plugin "tmux-plugins/tpm"

set -g @plugin "christoomey/vim-tmux-navigator"
set -g @plugin "tmux-plugins/tmux-resurrect"
set -g @plugin "tmux-plugins/tmux-continuum"
set -g @plugin "hendrikmi/tmux-cpu-mem-monitor"

set -g @resurrect-capture-pane-contents "on"
set -g @resurrect-strategy-nvim "session"
set -g @resurrect-dir "~/.config/tmux/resurrect"

# other config ...

run "~/.tmux/plugins/tpm/tpm"
```

## Acknowledgments & inspiration
- Hendrik's [minimal tmux layout](https://youtu.be/6Jgl5wphD00) & [CPU & memory plugin](https://github.com/hendrikmi/tmux-cpu-mem-monitor)
- The [catppuccin color palette](https://catppuccin.com/palette/)

## Contributing
If you have any input or recommendations, open a PR!

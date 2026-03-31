# Yazi

## Commands

- ya pkg list
- ya pkg upgrade

## Plugins

<https://github.com/yazi-rs/plugins/blob/main/smart-paste.yazi/README.md>
<https://github.com/yazi-rs/plugins/blob/main/smart-enter.yazi/README.md>

## Themes

<https://github.com/yazi-rs/flavors?tab=readme-ov-file>

- "catppuccin-macchiato"
- "tokyo-night"

## Config paths

- base: ~/.config/yazi/
- keymap: `~/.config/yazi/keymap.toml`
- themes: `~/.config/yazi/theme.toml`

## Shell Integration

```sh
function y() {
 local tmp="$(mktemp -t "yazi-cwd.XXXXXX")" cwd
 command yazi "$@" --cwd-file="$tmp"
 IFS= read -r -d '' cwd < "$tmp"
 [ "$cwd" != "$PWD" ] && [ -d "$cwd" ] && builtin cd -- "$cwd"
 rm -f -- "$tmp"
}
```

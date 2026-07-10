# ide-config

Personal configuration for workflow involving IDEs, terminals, GitHub, and terminal tools.

## Apps

- Ghostty
- Lazygit
- GitHub CLI
- gh-dash
- diffnav
- delta

## Install

Fedora:

```bash
sudo dnf install gh golang git-delta ghostty
go install github.com/jesseduffield/lazygit@latest
go install github.com/dlvhdr/diffnav@latest
gh extension install dlvhdr/gh-dash
```

Make sure Go binaries are available in the shell:

```bash
echo 'export PATH="$HOME/go/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

`git-delta` provides the `delta` binary used internally by `diffnav`.

## Restore Configs

Run from this repository root:

```bash
mkdir -p ~/.config/ghostty ~/.config/lazygit ~/.config/gh-dash ~/.config/diffnav
cp ghostty/config.ghostty ~/.config/ghostty/config
cp lazygit/config.yml ~/.config/lazygit/config.yml
cp gh-dash/config.yml ~/.config/gh-dash/config.yml
cp diffnav/config.yml ~/.config/diffnav/config.yml
```

## Verify

```bash
gh --version
gh extension list
lazygit --version
ghostty --version
delta --version
diffnav --version
```

## Notes

- `gh-dash` uses `diffnav` for PR diffs.
- `diffnav` needs `delta` in `PATH`.
- `diffnav` is configured with `startFoldersOpenDepth: -1` so changed files are visible without manually expanding folders.

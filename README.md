# zsh-gh-clone

Clone a GitHub repository into your workspace with one command!

## Example

```
$ GH_CLONE_WORKSPACE_DIR=~/develop/workspace
$ GH_CLONE_DEFAULT_GITHUB_USER=sei40kr

# equivalent to `git clone https://github.com/sei40kr/dotfiles ~/develop/workspace/sei40kr/dotfiles`
$ gh-clone dotfiles
```

## Install

### Install with [zplugin](https://github.com/zdharma/zplugin) (recommended)

```sh
zplugin light sei40kr/zsh-gh-clone
```

### Install with [zplug](https://github.com/zplug/zplug)

```sh
zplug sei40kr/zsh-gh-clone
```
## Customization

| Variable                       | Default Value                 | Description                                                          |
| :--                            | :--                           | :--                                                                  |
| `GH_CLONE_WORKSPACE_DIR`       | `''`                          | Workspace directory where you clone repositories                     |
| `GH_CLONE_DEFAULT_GITHUB_USER` | `"$(git config github.user)"` | Default GitHub user. If username omitted, this will be used instead. |

## Tips

### Clone a repository of yours via SSH

```
[url "git@github.com:sei40kr"]
  insteadOf "https://github.com/sei40kr"
```

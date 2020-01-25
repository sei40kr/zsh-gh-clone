# zsh-gh-clone

Clone a GitHub repository into your workspace with one command!

## Example

```zsh
GH_CLONE_WORKSPACE_DIR=~/develop/workspace
GH_CLONE_DEFAULT_GITHUB_USER=sei40kr

# equivalent to `git clone https://github.com/sei40kr/dotfiles ~/develop/workspace/sei40kr/dotfiles`
gh-clone dotfiles
```

## Install

### Install with [zinit](https://github.com/zdharma/zinit) (recommended)

```zsh
zinit ice trigger-load'!gh-clone'
zinit light sei40kr/zsh-gh-clone
```

### Install with [zplug](https://github.com/zplug/zplug)

```zsh
zplug sei40kr/zsh-gh-clone
```

## Customization

| Variable                       | Default Value                 | Description                                                          |
| :--                            | :--                           | :--                                                                  |
| `GH_CLONE_WORKSPACE_DIR`       | `''`                          | Workspace directory where you clone repositories                     |
| `GH_CLONE_DEFAULT_GITHUB_USER` | `"$(git config github.user)"` | Default GitHub user. If username omitted, this will be used instead. |

## Tips

### Clone a repository of yours via SSH

Configure your `.gitconfig` like shown below:

```gitconfig
[url "git@github.com:sei40kr"]
  insteadOf "https://github.com/sei40kr"
```

### Use different keys for different GitHub users

Configure your `.gitconfig` like shown below:

```gitconfig
[url "git@github-private:sei40kr"]
  insteadOf "https://github.com/sei40kr"
[url "git@github.com:sei40kr-work"]
  insteadOf "https://github.com/sei40kr-work"
```

Then specify a key to use in your `.ssh/config` too:

```ssh-config
Host github-private
  HostName github.com
  User git
  IdentityFile ~/.ssh/id_rsa_private
```

You also need to make sure the permission for `.ssh/config` set properly:

```zsh
chmod 600 ~/.ssh/config
```

## Similar Projects

- [ghq](https://github.com/motemen/ghq)
- [rrc](https://github.com/mopemope/rrc)

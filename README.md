# Setup computer

### iTerm2

- Download it [from here](https://iterm2.com/downloads.html).
- Load the [profile settings JSON](./iterm2/default-profile.json) in _Settings > Profiles > Other Actions... > Import JSON Profiles..._

---

### Homebrew

Install it with the following command.
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
---

### Git

```shell
brew install git
```

#### Config

```shell
[user]
	name =
	email =
[merge]
	tool = meld
[mergetool "meld"]
	path = /Applications/Meld.app/Contents/MacOS/meld
```

---

### Install last version of bash:

```shell
brew install bash
```

---

### Auto completion for bash and Docker:

```shell
brew install bash-completion
brew install docker-completion
```
---

### Pyenv

- Install dependencies:

    ```shell
    brew update
    brew install openssl readline sqlite3 xz zlib
    ```

- Install _pyenv_:

    ```shell
    brew install pyenv
    ```

- Update the _.bash_profile_ file to ensure autocomplete for _pyenv_:

    ```shell
    echo -e 'if command -v pyenv 1>/dev/null 2>&1; then\n  eval "$(pyenv init -)"\nfi' >> ~/.bash_profile
    source ~/.bash_profile
    ```

---

### Oh My Posh

- Installation:

    ```shell
    brew install jandedobbeleer/oh-my-posh/oh-my-posh
    ```

- Update:

    ```shell
    brew update && brew upgrade oh-my-posh
    ```

- Update the _.bash_profile_ file to change your terminal prompt:

    ```shell
    echo -e 'eval "$(oh-my-posh init bash)"' >> ~/.bash_profile
    source ~/.bash_profile
    ```

- Or if you want set up a specific theme:

    ```shell
    echo -e 'eval "$(oh-my-posh init bash --config /usr/local/opt/oh-my-posh/themes/{theme_name}.json)"' >> ~/.bash_profile
    source ~/.bash_profile
    ```

- To show Python virtual environment on your prompt, you should add the following code in the first segment of the theme you are using.

    ```json
    {
        "type": "python",
        "style": "plain",
        "foreground": "yellow",
        "template": " \uE235 ({{ .Venv }}) {{ .Full }} "
    }
    ```

- Example of a minimal prompt json file that shows the prompt like this: "time [python env] user@host path [git branch]"

    ```json
    {
        "$schema": "https://raw.githubusercontent.com/JanDeDobbeleer/oh-my-posh/main/themes/schema.json",
        "palette": {
            "black": "#282c34",
            "red": "#e06c75",
            "green": "#98c379",
            "yellow": "#e5c07b",
            "blue": "#61afef",
            "magenta": "#c678dd",
            "cyan": "#56b6c2",
            "white": "#dcdfe4",
            "foreground": "#dcdfe4",
            "background": "#282c34"
        },
        "terminal_background": "p:background",
        "console_title_template": "{{ .UserName }}@{{ .HostName }}",
        "blocks": [
            {
                "alignment": "left",
                "newline": false,
                "segments": [
                    {
                        "foreground": "#c7945b",
                        "properties": {
                            "time_format": "15:04:05"
                        },
                        "style": "plain",
                        "template": "[{{ .CurrentDate | date .Format }}] ",
                        "type": "time"
                    },
                    {
                        "style": "plain",
                        "foreground": "yellow",
                        "template": "({{ .Venv }}) {{ .Full }} ",
                        "type": "python"
                    },
                    {
                        "foreground": "#c7945b",
                        "style": "plain",
                        "template": "{{ .UserName }}@{{ .HostName }} ",
                        "type": "session"
                    },
                    {
                        "foreground": "blue",
                        "style": "plain",
                        "properties": {
                            "style": "agnoster"
                        },
                        "template": "{{ .Path }} ",
                        "type": "path"
                    },
                    {
                        "properties": {
                            "branch_gone_icon": "\u274e",
                            "branch_identical_icon": "\uf14a",
                            "fetch_status": true,
                            "fetch_stash_count": true,
                            "fetch_worktree_count": true
                        },
                        "style": "plain",
                        "template": "{{ if or (.Working.Changed) (.Staging.Changed) (gt .StashCount 0) }}<p:magenta>{{ .HEAD }}</>{{ else }}<p:green>{{ .HEAD }}</>{{ end }}{{ if (gt .Ahead 0)}}<p:cyan>{{ .BranchStatus }}</>{{ end }}{{ if (gt .Behind 0)}}<p:cyan>{{ .BranchStatus }}</>{{ end }}{{ if .Staging.Changed }} <p:green>{{ .Staging.String }}</>{{ end }}{{ if .Working.Changed }} <p:red>{{ .Working.String }}{{ end }}",
                        "type": "git"
                    }
                ],
                "type": "prompt"
            },
            {
                "alignment": "left",
                "newline": true,
                "segments": [
                    {
                        "foreground": "p:foreground",
                        "properties": {
                            "always_enabled": true
                        },
                        "style": "plain",
                        "template": "{{ if gt .Code 0 }}<p:red>({{ .Code }}) </>{{ else }}<p:green>({{ .Code }}) </>{{ end }}> ",
                        "type": "exit"
                    }
                ],
                "type": "prompt"
            }
        ],
        "disable_notice": true,
        "version": 2
    }
    ```

---

### VS Code

- Extensions

    - KevinRose.vsc-python-indent
    - PKief.material-icon-theme
    - ahmadalli.vscode-nginx-conf
    - eamodio.gitlens
    - mechatroner.rainbow-csv
    - monokai.theme-monokai-pro-vscode
    - ms-azuretools.vscode-docker
    - ms-python.black-formatter
    - ms-python.isort
    - ms-python.python
    - ms-python.vscode-pylance
    - redhat.vscode-yaml
    - tamasfe.even-better-toml
    - vscode-icons-team.vscode-icon

- You can show the settings file [here](./vscode/settings.json).

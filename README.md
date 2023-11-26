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

---

### VS Code

- Extensions

    - tamasfe.even-better-toml
    - ms-azuretools.vscode-docker
    - eamodio.gitlens
    - ms-kubernetes-tools.vscode-kubernetes-tools
    - ms-vscode.makefile-tools
    - PKief.material-icon-theme
    - monokai.theme-monokai-pro-vscode
    - ms-python.python
    - redhat.vscode-yaml
    - vscode-icons-team.vscode-icons
    - mechatroner.rainbow-csv
    - william-voyek.vscode-nginx

- You can show the settings file [here](./vscode/settings.json).

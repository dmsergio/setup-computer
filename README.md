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

### __Git__

```shell
brew install git
```

---

### Install last version of __bash__:

```shell
brew install bash
```

---

### Auto completion for __bash__ and __Docker__:

    ```shell
    brew install bash-completion
    brew install docker-completion
    ```
---

### __Pyenv__

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

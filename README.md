# Setup computer

### iTerm2

- Download it [from here](https://iterm2.com/downloads.html).
- Load the [profile settings JSON](./iterm2/default-profile.json) in _Settings > Profiles > Other Actions... > Import JSON Profiles..._

### Homebrew

```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

- Install last version of _bash_:

    ```shell
    brew install bash
    ```

- Install last version of _Git_:

    ```shell
    brew install git
    ```

- Auto completion for _bash_ and _Docker_:

    ```shell
    brew install bash-completion
    brew install docker-completion
    ```

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


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

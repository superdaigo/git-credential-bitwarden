# git-credential-bitwarden

## What is this?

This scirpt is git subcommand `credential-bitwarden` which manages git credential using Bitwarden CLI.

## Why this is created?

I personally use Bitwarden to manage my credentials. So I'd like to store GitHub access key using Bitwarden on my Linux PC.
For macOS, there is an embedded integration `credential-osxkeychain` in Git command but it doesn't work on Linux.


## How it works

The command is called by git bommand if needed.
To use the integration, you have have valid BW_SESSION environment variable.

## Requirements

- Python 3 (Tested by Python 3.7)
- Bitwarden CLI (https://github.com/bitwarden/cli)
- Valid BW_SESSION environment valiable

## How to install

### 1. Download the script `git-credential-bitwarden` under a directory in your PATH

If you don't have proper directory to install, the following commands will work.
```
$ mkdir ${HOME}/bin
$ export ${HOME}/bin:${PATH} >> ${HOME}/.bashrc
$ source .bashrc
```

Download the file `git-credential-bitwarden`.
```
$ curl -o ${HOME}/bin/git-credential-bitwarden https://github.com/superdaigo/git-credential-bitwarden/git-credential-bitwarden
```

### 2. Change file mode to 755

```
$ chmod +x ${HOME}/bin/git-credential-bitwarden
```

### 3. Configure git credential helper

```
$ git config --global credential.helper bitwarden
```


## How to uninstall

### 1. Delete downloaded script

```
$ rm ${HOME}/bin/git-credential-bitwarden
```

### 2. Remove config git credential.helper

```
$ git config --global --unset credential.helper
```
You might be able to remove ${HOME}/bin directory and PATH configuration from your `${HOME}/.bashrc` file.

# qsh

**Easy q for anything: reading lists, pending tasks... Now written in POSIX shell!**

This program is designed to work with full compatibility with [fdavidcl's q](https://github.com/fdavidcl/q).

## Dependencies

A POSIX compliant shell, so basically none!

## Installation

Copy `qsh` to your `.local/bin` or other directory in your `$PATH`.
You may need to `chmod +x q`.

```sh
mkdir -p ~/.local/bin && cp qsh ~/.local/bin
```

You can set an alias in your shell `.rc` file to call the program as `q` or call it with some default arguments:

```sh
alias q=qsh
alias qsh="qsh -d $HOME/.myq -f mainq"
```

## Defaults

If not especified, `qsh` will load the following variables:

| **Variable** | **Value**      | **Description**      |
| ------------ | -------------- | -------------------- |
| `qshdir`     | `"$HOME/.q/"`  | Default q directory. |
| `qshfile`    | `"$qshdir""q"` | Default q file.      |

## Arguments

Arguments are defined as *dash options* (`--?.\+`) followed by a space and their corresponding value.
Non-flag arguments will allways be parsed as strings to enter in the q **in argv order**.

| **Argument**        | **Description**                                                   |
| ------------------- | ----------------------------------------------------------------- |
| `-d`, `--directory` | Set a new q directory other than the default.                     |
| `-f`, `--file`      | Set a new q file in the current directory other than the default. |

Bear in mind that changing the directory will **always** update the file path.

## Usage

### Pop the first element:

You can pop the first element from the default or an specific q if you don't add any non-flag arguments.

```sh
qsh
qsh -d $HOME/.myq -f mainq
```

### Add an element at the back of the q:

Same as before, you can add the flags in any order.

```sh
qsh https://arxiv.org/abs/1811.12044
qsh -d $HOME/.myq -f mainq https://arxiv.org/abs/1811.12044
qsh https://arxiv.org/abs/1811.12044 -d $HOME/.myq -f mainq
```

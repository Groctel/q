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

You can set an alias in your shell `.rc` file to call the program as `q`:

```sh
alias q=qsh
```

## Usage

Pop something from your q:

```sh
qsh
```

Add something to your q:

```sh
qsh https://arxiv.org/abs/1811.12044
```

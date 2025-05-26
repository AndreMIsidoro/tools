# feroxbuster

## Overview

Feroxbuster is a tool designed for directory and file busting, which is commonly used in web application security testing.

## Installation

```shell
sudo apt update && sudo apt install -y feroxbuster
```

## Usage

Basic usage:

```shell
feroxbuster --url http://bigbang.htb
```

Output to a file

```shell
feroxbuster --url htpp://bigbang.htb -o feroxbuster.out
```
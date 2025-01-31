# Zettelkasten

A simple Zettelkasten setup using Vim + FZF + Ripgrep

![Zettelkasten](./banner.jpeg)

## What is a zettelkasten?

> The zettelkasten (German: "slip box") is a knowledge management and note-taking method used in research and study. 

[Wikipedia](https://en.wikipedia.org/wiki/Zettelkasten)

The zettelkasten method consists of taking multiple individual notes, tagging and relating them together, in order to
build a private knowledge base.

## Why?

I was inspired by [this post](https://superorganizers.substack.com/p/how-to-build-a-learning-machine), and by how the
author built his own setup using Unix tools. I wanted a similar, but slightly different setup.
By the way, his work is also [on Github](https://github.com/sirupsen/zk)

## How?

### Philosophy

Each zettel (probably not a real world, but I'll use that to refer to each individual note) is a markdown file, named
with a timestamp and a title.

Zettels can have tags (e.g.: `#programming`, `#quote`, `#really-good-advice`), as well as sources (e.g.: `@tim-ferriss`,
`@mom`, `@myself`).

They're otherwise plain markdown files, write whatever you want, in whatever format you wish. Here's a sample:

```
# 2020-07-17-11-30-optimization.md

Premature optimization is the root of all evil

**I opted to use markdown italic syntax for personal comments**

#quote #programming
@donald-knuth
```

You can then navigate your knowledge base by searching for tags, sources, or just plain full-text search.

All of this is powered by:
- [Vim](https://www.vim.org) ([Neovim](https://neovim.io) works too)
- [Fzf](https://github.com/junegunn/fzf)
- [Ripgrep](https://github.com/BurntSushi/ripgrep)
)

More tooling may be added down the line, but for now this simple setup serves me well.

### Installation

1. Make sure you have the `fzf`, `rg` commands working on your shell, as well as
   the [fzf.vim](https://github.com/junegunn/fzf.vim) Vim plugin.

2. Clone the repo to some place:

```sh
git clone git@github.com:josh-tracey/zk.git $HOME/.zk
```

3. Add the `bin` directory to your path

```sh
# add this to your .bashrc / .zshrc / .whateverrc
export PATH="$HOME/.zk/bin:$PATH"
```

4. Setup the needed `$ZK_PATH` variable, pointing to where you want your knowledge base to be:

```sh
# add this to your .bashrc / .zshrc / .whateverrc
export ZK_PATH="$HOME/zettelkasten"
```

5. Start using it

```sh
# create a new zettel
$ zk new "An Awesome Quote"

# search by tags
$ zk tags

# search by sources
$ zk sources

# full-text search the entire zettelkasten
$ zk search

# get help
$ zk help
```

## Contributing

Feel free to do so.

Pull requests, issues, or even a [tweet](https://twitter.com/naps62) is welcome.

---
title: "How to search & replace all occurences in vim?"
date: 2023-02-22T07:00:00+01:00
slug: 2023-02-22_search_replace_vim
type: posts
draft: false
categories:
  - vim
  - knowledge
tags:
  - knowledge
  - vim
---

I always struggle to remember things that I don't use often. Here is my 
attempt to keep my knowledge somewhere else than in my head.  
One of them is specific to vim.  

# How to search a specific string pattern inside a project and replace all its occurences *easily*.

Let's start with the initial statement, I want to replace all the `linux` 
occurences by `OpenBSD`.

## Find files that validate the pattern predicate

Run:  
`:vimgrep /linux/gj **/*`

* `**/*` to search on all files recursively 
* `g` flag to search for all occurences in each line
* `j` flag to avoid vim to jump automatically on the first occurence

Once the command ran, vim will populate the quickfix list with all the `linux`
occurences. To see the list, run `:copen`.

## Replace or subsitute all the linux occurences

Here comes vim's super power, running a command for each line in the quickfix list.  

Run:  
`:cfdo %s/linux/OpenBSD/gc | update`

* `%s/linux/OpenBSD` is the subsitute pattern
* `g` flag replaces all occurences in each line
* `c` flag asks to confirm each subsitution
* `update` to make sure the file is saved before moving to the next one

For more information on those previous commands, you can try:
* `:help vimgrep`
* `:help cfdo`


All of these info are essentially copied from a stackexchange [comment](https://vi.stackexchange.com/a/10310).


*Thx.*

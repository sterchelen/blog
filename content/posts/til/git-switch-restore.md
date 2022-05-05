---
title: "TIL: git switch & restore"
date: 2021-08-02T21:35:55+02:00
categories: ["til"]
draft: true
---

# Introduction
While reading the `git-checkout` man page on my laptop, I saw this section:
{{< image src="/images/git-checkout.png" linked=false >}}  
I've never heard about this two commands `git switch` and `git restore` before reading this section.
This gonna make a great occasion to write my first blog post :).

# History
Everyone using `git` on a daily basis is used to use `git checkout`, to:
- create to a new branch (1)
- to switch to a branch (2)
- to move your HEAD to a specific commit (3)
- to discard your local changes and restore the impacted files to a particular index (4)

{{< admonition note "Branch usage" >}}
	git checkout my_branch (1)	
	git checkout -b my_new_branch (2)
	git checkout deb5843390912a459f9719f20381a30ac08a5c3c (3)
{{</ admonition >}}

{{< admonition note "File usage" >}}
	git checkout coding_game (1)
	rm my_beautiful_file.go (2)
	git checkout -- my_beautiful_file.go (3)

----
1. switch to coding_game branch
2. remove my_beautiful_file.go file
3. restore my_beautiful_file.go from the index
{{</ admonition >}}

`git checkout` do a lot of things, maybe too much. We could argue that `git checkout` is just working
with index but in the e

# Switch


# Restore

# Conclusion

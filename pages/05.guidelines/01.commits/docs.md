---
title: Commit Style Guide
taxonomy:
    category: docs
---

> This is a draft any comments or suggestions are welcome

> Unitex/GramLab is an open source, cross-platform, multilingual, lexicon- and grammar-based corpus processing suite. This guide presents a compilation of guidelines to write commit messages on a Unitex/GramLab source code repository.

> **The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119)**

# 1. Commit messages

Commit messages MUST be composed of a commit subject (first line) and OPTIONALLY by followed by a blank line (second line) and a commit body (third line):

- The first line is the commit subject and is treated as the subject of an email

- The second line MUST be blank and MUST NOT have leading or trailing whitespaces

- The third line is the commit body and is intended to describe why a change is being made

## 1.1 Commit subject

<div style="text-align:center">
    <img src="https://s28.postimg.org/i6g05kpel/commit.png"/>
</div>

<!---
#Unigraph
SIZE 1318 840
FONT Inconsolata:  10
OFONT Inconsolata:B 12
BCOLOR 16777215
FCOLOR 0
ACOLOR 13487565
SCOLOR 16711680
CCOLOR 255
DBOXES y
DFRAME y
DDATE y
DFILE y
DDIR n
DRIG n
DRST n
FITS 100
PORIENT L
#
12
"<E>" 51 299 2 8 11 
"" 983 298 0 
"break+exp+tmp+major+minor+sec+<E>" 232 202 1 4 
"bin+ci+doc+<E>" 160 202 1 2 
"deprecat+enhance+fix+feature+refactor+remove" 317 202 1 5 
"\#<NB>+<E>" 430 202 1 6 
"]" 509 202 1 7 
"\" \"" 555 202 1 8 
"Add+Allow+Avoid+Change+Create+Delete+Disallow+Disable+Enable+Improve+Init+Integrate+Merge+Move+Rename+Replace+Resolve+Revert+Update+Use" 675 298 1 9 
"<WORD>+<NB>+<PNC>+." 794 298 2 10 9 
"<WORD>+<NB>" 900 298 1 1 
"[" 121 202 1 3 
--->

- **MUST** be between 18 and 69 characters long. The best practice is not exceeded 50, GitHub will warn you if you go past this limit and will truncate any subject line longer than 69 characters with an ellipsis

- **MUST** have the following format: `(<tag> )?<Message>`

- **MAY** start with a commit tag (`<tag>`), valid commit tags are described below

- **MUST** have a commit message (`<Message>`), valid commit messages are described below

### 1.1.1 Commit tags 

- **MAY** prefix the commit message with a valid tag expression

- **SHOULD** use lowercase letters 

- **MUST** be surrounded by brackets []

- **MUST** have the following format: `FT? CL? CT IN?`

#### File types (optional) (`FT`):


| Tag             | Description                                       | Changes affecting            |
| --------------- | :-----------------------------------------------: | :---------------------:      |
| `bin`           | Change related to *binary* files                  | binary files                 |
| `ci`            | Change related to *continuous integration* files  | continuous integration files |
| `doc`           | Change related to *documentation* files           | documentation files          |
| (Nothing)       | Change related to source code files               | source code files          |


#### Change level (optional) (`CL`):

| Tag             | Description                                  |
| --------------- | :------------------------------------------: |
| `break`         | Breaking change                              |
| `exp`           | Experimental change                          |
| `tmp`           | Temporal change                              |
| `major`         | Major change                                 |
| `minor`         | Minor change                                 |
| `sec`           | Vulnerability-related change                 |
| (Nothing)       | Normal change                                |

#### Change type (mandatory) (`CT`)


| Tag            | Description                                         | Changes affecting       |
| -------------- | :-------------------------------------------------: | :---------------------: |
| `deprecat`     | Deprecation of a once-stable feature                | source files            |
| `enhance`      | Enhancement in existing functionality               | source files            |
| `fix`          | Fix for any bug                                     | source files            |
| `feature`      | New feature or functionality                        | source files            |
| `refactor`     | Improve coding style, comments                      | source files            |
| `remove`       | Remove a feature                                    | source files            |


#### Issue number (optional) (`IN`):

| Tag             | Description                                       | Changes affecting       |
| --------------- | :-----------------------------------------------: | :---------------------: |
| `#n`            | Refer the issue #n in the same repository         | source files            |


### 1.1.2 Commit message

- **MUST** start with a capitalized word 

- **MAY** start with a common operation verb (`OV`), operation verbs are described below

- **SHOULD** use imperative language: `Resolve merge conflict` and neither `Resolved merge conflict` nor `Resolves merge conflict`

- **MUST** be able to complete the following sentence: `If applied, this commit will <Message>`, e.g.: `If applied, this commit will resolve merge conflict` 

- **MUST NOT** end with a full stop

#### Common operation verbs (`OV`)


| Operation     |
| ------------- |
| `Add`         |
| `Allow`       |
| `Avoid`       |
| `Change`      |
| `Check`       |
| `Create`      |
| `Delete`      |
| `Disallow`    |
| `Disable`     |
| `Enable`      |
| `Improve`     |
| `Init`        |
| `Integrate`   |
| `Merge`       |
| `Move`        |
| `Rename`      |
| `Replace`     |
| `Replace`     |
| `Resolve`     |
| `Revert`      |
| `Update`      |
| `Use`         |


## 1.2 Commit body

- **SHOULD NOT** exceed 72 characters
 
- **MAY** be free-form and **SHOULD** use normal punctuation and capital letters where appropriate

- **SHOULD** refer one or several issues. 

- **MAY** be formatted using [Markdown syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

- **MUST** clearly specify any drawback or limitation of the committed code

- **MAY** highlight any further improvement on the committed code


## 1.3 Examples

- Not every commit requires a tagged subject

``
Update README.md
``

``
Change UI to support generic graphs
``

- Not every commit requires a body

``
[fix #15] Resolve segmentation fault on LocateTfst
``

``
[doc enhance] Add more information about file types
``

``
[minor refactor] Replace tabs by spaces
``

- Sometimes, a commit requires a body to include further explanations and/or context

```
[feature #24] Add find and replace on graphs

This commit adds a find and replace feature on graph's boxes.
The find and replace dialog allows user...

Resolves #24
See also #23
```

# 2. Special triggers


| Trigger      | Description                                                   | Action                |
| ------------- | :----------------------------------------------------------: | :-------------------: |
| `[ci skip]`   | Don't run a build for this commit                            | Control CI            |
| `[ci release]`| Create a distribution release for this commit only on master | Control CI            |
| `Close #n`    | Close the issue #n in the same repository                    | Control issues        |
| `#n`          | Refer the issue #n in the same repository                    | Autolink reference    |
| `caf6218`     | Refers to a commit hash in the same repository               | Autolink reference    |
| `@user`       | Refer a `user` on GitHub                                     | Autolink reference    |
| `@organization/team`| Refer a `organization/team` on GitHub                  | Autolink reference    |


# 3. Best practices

- [Commit early and often](http://c2.com/cgi/wiki?CommitEarlyAndOften)

- Only perform one *logical change* per commit

- Give other users and members the credit they deserve, and perhaps even expect from you

- If you are committing code on behalf of other member use the `--author` option for `git commit`

- Before committing, inspect your changes

- Before committing, check if your commit message follow the guidelines

## Attribution

These guidelines were initially contributed by Cristian Martinez as part of the DataMaTex project developed by [Amabis SARL](http://www.amabis.fr) with the collaboration of the [LIGM](http://infolingu.univ-mlv.fr/). This document is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.


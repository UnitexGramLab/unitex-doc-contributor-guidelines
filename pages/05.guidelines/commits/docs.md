---
title: Commit Style Guide
taxonomy:
    category: docs
---

> This is a draft any comments or suggestions are welcome

Unitex/GramLab is an open source, cross-platform, multilingual, lexicon- and grammar-based corpus processing suite. This guide presents a compilation of guidelines to write commit messages on a Unitex/GramLab source code repository.

> The key words "MUST", "MUST NOT", "REQUIRED", "SHALL", "SHALL NOT", "SHOULD", "SHOULD NOT", "RECOMMENDED", "MAY", and "OPTIONAL" in this document are to be interpreted as described in [RFC 2119](http://tools.ietf.org/html/rfc2119)

# 1. Commit messages

Commit messages MUST be composed by a commit subject (first line) and OPTIONALLY by accompanied with a blank line (second line) followed by a commit body (third line):

- The first line is the commit subject and is treated as the subject of an email

- The second line MUST be blank and MUST NOT have leading or trailing whitespaces

- The third line is the commit body and is intended to describe why a change is being made

## 1.1 Commit subject

- **MUST** be between 18 and 69 characters long. The best practice is not exceeded 50, GitHub will warn you if you go past this limit and will truncate any subject line longer than 69 characters with an ellipsis

- **MUST** follow the next format: `(<tag> )?<Message>`

- **MAY** start with a commit tag (`<tag>`), valid commit tags are described below

- **MUST** have a commit message (`<Message>`), valid commit messages are described below

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

### 1.1.1 Commit tags 

- **MAY** prefix the commit message with a valid tag expression

- **SHOULD** use lowercase letters 

- **MUST** be surrounded by brackets

- **MUST** follow the next format: `FT? CL? CT IN?`

#### File types (`FT`):

<!---
| Tag             | Description                                       | Changes affecting       |
| --------------- | :-----------------------------------------------: | :---------------------: |
| `bin`         | Change related to *binary* files                  | binary files            |
| `doc`         | Change related to *documentation* files           | documentation files     |
--->

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Tag</th>
<th>Description</th>
<th>Changes affecting</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>bin</code></td>
<td>Change related to <em>binary</em> files</td>
<td>binary files</td>
</tr>
<tr>
<td><code>doc</code></td>
<td>Change related to <em>documentation</em> files</td>
<td>documentation files</td>
</tr>
</tbody>
</table>

#### Change level (`CL`):

<!---
| Tag             | Description                                       | Changes affecting       |
| --------------- | :-----------------------------------------------: | :---------------------: |
| `minor`       | Minor code change                                 | source files            |
| `exp`         | Experimental code change                          | source files            |
| `sec`         | Vulnerability-related code change                 | source files            |
--->

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Tag</th>
<th>Description</th>
<th style="text-align:center">Changes affecting</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>minor</code></td>
<td>Minor code change</td>
<td style="text-align:center">source files</td>
</tr>
<tr>
<td><code>exp</code></td>
<td>Experimental code change</td>
<td style="text-align:center">source files</td>
</tr>
<tr>
<td><code>sec</code></td>
<td>Vulnerability-related code change</td>
<td style="text-align:center">source files</td>
</tr>
</tbody>
</table>

#### Change type (`CT`)

<!---
| Tag             | Description                                         | Changes affecting       |
| --------------- | :-------------------------------------------------: | :---------------------: |
| `deprecat`    | Deprecation of a once-stable feature                | source files            |
| `enhance`     | Enhancement in existing functionality               | source files            |
| `fix`         | Fix for any bug                                     | source files            |
| `feature`     | New feature or functionality                        | source files            |
| `refactor`    | Improve coding style, comments                      | source files            |
--->

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Tag</th>
<th>Description</th>
<th style="text-align:center">Changes affecting</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>enhance</code></td>
<td>Enhance a functionality already in place</td>
<td style="text-align:center">source files</td>
</tr>
<tr>
<td><code>fix</code></td>
<td>Fix for an untracked/tracked issue</td>
<td style="text-align:center">source files</td>
</tr>
<tr>
<td><code>feature</code></td>
<td>New functionality</td>
<td style="text-align:center">source files</td>
</tr>
<tr>
<td><code>refactor</code></td>
<td>Improve coding style, comments</td>
<td style="text-align:center">source files</td>
</tr>
</tbody>
</table>

#### Issue number (`IN`):

<!---
| Tag             | Description                                       | Changes affecting       |
| --------------- | :-----------------------------------------------: | :---------------------: |
| `#n`          | Refer the issue #n in the same repository         | source files            |
--->

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Tag</th>
<th>Description</th>
<th style="text-align:center">Changes affecting</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>#n</code></td>
<td>Refer the issue #n in the same repository</td>
<td style="text-align:center">source files</td>
</tr>
</tbody>
</table>

### 1.1.2 Commit message

- **MUST** start with a capitalized word 

- **MAY** start with a common operation verb (`OV`), operation verbs are described below

- **SHOULD** use imperative language: `Resolve merge conflict` and neither `Resolved merge conflict` nor `Resolves merge conflict`

- **MUST** be able to complete the following sentence: `If applied, this commit will <Message>`, e.g.: `If applied, this commit will resolve merge conflict` 

- **MUST NOT** end with a full stop

#### Common operation verbs (`OV`)

<!---
| Tag             | Description                                       | Changes affecting       |
| --------------- | ------------------------------------------------- | :---------------------: |
| `Add`         | Add                                               | any file                |
| `Allow`       | Allow                                             | any file                |
| `Avoid`       | Avoid                                             | any file                |
| `Change`      | Change                                            | any file                |
| `Create`      | Create                                            | any file                |
| `Delete`      | Remove                                            | any file                |
| `Disallow`    | Disallow                                          | any file                |
| `Improve`     | Improve                                           | any file                |
| `Init`        | Repository initialization                         | repository              |
| `Merge`       | Merge                                             | any file                |
| `Move`        | Move                                              | any file                |
| `Remove`      | Remove                                            | any file                |
| `Replace`     | Replace                                           | any file                |
| `Resolve`     | Resolve                                           | any file                |
| `Update`      | Update                                            | any file                |
| `Use`         | Use                                               | any file                |
--->

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Tag</th>
<th>Description</th>
<th style="text-align:center">Changes affecting</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>Add</code></td>
<td>Add</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Allow</code></td>
<td>Allow</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Avoid</code></td>
<td>Avoid</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Change</code></td>
<td>Change</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Create</code></td>
<td>Create</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Delete</code></td>
<td>Remove</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Disallow</code></td>
<td>Disallow</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Improve</code></td>
<td>Improve</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Init</code></td>
<td>Repository initialization</td>
<td style="text-align:center">repository</td>
</tr>
<tr>
<td><code>Merge</code></td>
<td>Merge</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Move</code></td>
<td>Move</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Remove</code></td>
<td>Remove</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Replace</code></td>
<td>Replace</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Resolve</code></td>
<td>Resolve</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Update</code></td>
<td>Update</td>
<td style="text-align:center">any file</td>
</tr>
<tr>
<td><code>Use</code></td>
<td>Use</td>
<td style="text-align:center">any file</td>
</tr>
</tbody>
</table>

## 1.2 Commit body

- **SHOULD NOT** exceed 72 characters long
 
- **MAY** be free-form and **SHOULD** use normal punctuation and capital letters where appropriate

- **SHOULD** refer one or several issues. 

- **MAY** be formatted using [Markdown syntax](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)

- **MUST** cleary specify any drawback or limitation on the committed code


## 1.3 Examples

- Not every commit requires a tagged subject

``
Update README.md
``

``
Change UI to support generic graphs
``

- Not every commit requires both a subject and a body

``
[fix #15] Resolve segmentation fault on LocateTfst
``

``
doc enhance: Add more information about file types
``

``
minor refactor: Replace tabs by spaces
``

- Others commits requires a body to include further explanations and/or context

``
[feature #24] Add find and replace on graphs

This commit adds a find and replace feature on graph's boxes.
The find and replace dialog allows user...

Resolves #24
See also #23
``

# 2. Special triggers

<!---
| Trigger         | Description                                             | Action                  |
| --------------- | :-----------------------------------------------------: | :---------------------: |
| `[ci skip]`   | Don't run a build for this commit                       | Control CI              |
| `[ci release]`| Create a distribution release for this commit on master | Control CI              |
| `fix #n`      | Close the issue #n in the same repository               | Control issues          |
| `#n`          | Refer the issue #n in the same repository               | Autolink reference    |
| `caf6218`     | Refer a commit hash in the same repository              | Autolink reference    |
| `@user`       | Refer a `user` on GitHub                              | Autolink reference    |
| `@organization/team`| Refer a `organization/team` on GitHub           | Autolink reference    |
--->

<table class="table table-striped table-bordered">
<thead>
<tr>
<th>Trigger</th>
<th>Description</th>
<th style="text-align:center">Action</th>
</tr>
</thead>
<tbody>
<tr>
<td><code>[ci skip]</code></td>
<td>Don’t run a build for this commit</td>
<td style="text-align:center">Control CI</td>
</tr>
<tr>
<td><code>[ci release]</code></td>
<td>Create a distribution release for this commit on master</td>
<td style="text-align:center">Control CI</td>
</tr>
<tr>
<td><code>fix #n</code></td>
<td>Close the issue #n in the same repository</td>
<td style="text-align:center">Control issues</td>
</tr>
<tr>
<td><code>#n</code></td>
<td>Refer the issue #n in the same repository</td>
<td style="text-align:center">Autolink reference</td>
</tr>
<tr>
<td><code>caf6218</code></td>
<td>Refer a commit hash in the same repository</td>
<td style="text-align:center">Autolink reference</td>
</tr>
<tr>
<td><code>@user</code></td>
<td>Refer a <code>user</code> on GitHub</td>
<td style="text-align:center">Autolink reference</td>
</tr>
<tr>
<td><code>@organization/team</code></td>
<td>Refer a <code>organization/team</code> on GitHub</td>
<td style="text-align:center">Autolink reference</td>
</tr>
</tbody>
</table>

# 3. Best practices

- [Commit early and often](http://c2.com/cgi/wiki?CommitEarlyAndOften)

- Only perform one *logical change* per commit

- Give other users and members the credit they deserve, and perhaps even expect from you

- If you are committing code on behalf of other member use the `--author` option for `git commit`

- Before committing, inspect your changes

- Before committing, check if your commit message follow the guidelines

# 4. Generating a changelog

According to [Keep a Changelog](http://keepachangelog.com/), whose moto is "Don’t let your friends dump git logs into CHANGELOGs™", a change log *is a file which contains a curated, chronologically ordered list of notable changes for each version of a project.*

- `deprecated`: for a once-stable feature not recommended to use in upcoming releases
- `enhanced`: for enhancements in existing functionality
- `fixed`: for any bug fixes
- `featured`: for new features
- `removed`: for features removed in this release

## Attribution

These guidelines were initially contributed by Cristian Martinez as part of the DataMaTex project developed by [Amabis SARL](http://www.amabis.fr) with the collaboration of the [LIGM](http://infolingu.univ-mlv.fr/). This document is licensed under a Creative Commons Attribution-ShareAlike 3.0 Unported License.


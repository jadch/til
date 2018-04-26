# TIL

### Bash

* Removing a directory and its contents: `rm -rf [dirname]`
* Moving a directory and its contents: `mv source/ target/`
* Copying a directory and its contents: `cp -r source/ target/` 
* Printing a file line by line:̀ `cat [file] | more` 
* To rename a single file just use `mv`!


### npm

* Checking which version of npm is running: `npm -v`
* Going back to a previous version of npm *(for example npm 5)*: `npm install -g npm@5`

### Git

* Comparing the last two commits: `git diff HEAD^ HEAD`
* Limiting the diff to one file: `git diff HEAD^ HEAD -- [filename]`
* Listing all branches: `git branch -r`
* Copying the content of a branch to a new one: `git checkout -b new_branch old_branch`
* Going back to head while saving local modifications: `git stash`
* Undoing a `git stash`: `git stash pop`


### Javascript Debugging

* Using `console.group("Group name")`, logging... and then `console.groupEnd()`


### Flow

* Ignore an error on the next line with: `// $FlowFixMe`
* Doing an enum in Flow: `"success" | "fail"`
* Enum as object keys: `{ ["success" | "fail"]: true }`
* Object examples:
  * `{ [string]: Array<string> }` 

### Eslint

* Ignoring a rule in a file (for example max-lines): `/* eslint max-lines: 1 */`
* Ignoring an error in the next line: `/* eslint-disable-next-line id-length */`

### Kaggle CLI

* Configuring the CLI: `kg config -g -u [username] -p [password] -c [competition]`
* Downloading competition data: `kg download`

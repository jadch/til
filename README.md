# TIL

### Bash

* Removing a directory and its contents: `rm -rf [dirname]`
* Moving a directory and its contents: `mv source/ target/`
* Copying a directory and its contents: `cp -r source/ target/` 
* Printing a file line by line:̀ `cat [file] | more` 
* To rename a single file just use `mv`!

### Git

* Comparing the last two commits: `git diff HEAD^ HEAD`
* Limiting the diff to one file: `git diff HEAD^ HEAD -- [filename]`
* Listing all branches: `git branch -r`
* Copying the content of a branch to a new one: `git checkout -b new_branch old_branch`


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

### Kaggle CLI

* Configuring the CLI: `kg config -g -u [username] -p [password] -c [competition]`
* Downloading competition data: `kg download`

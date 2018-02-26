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


### Javascript Debugging

* Using `console.group("Group name")`, logging... and then `console.groupEnd()`


### Flow

* Ignore an error on the next line with: `// $FlowFixMe`
* Object examples:
  * `{ [string]: Array<string>}` 


### Kaggle CLI

* Configuring the CLI: `kg config -g -u [username] -p [password] -c [competition]`
* Downloading competition data: `kg download`

# TIL

### Bash

* Removing a directory and its contents: `rm -rf [dirname]`
* Moving a directory and its contents: `mv source/ target/`
* Copying a directory and its contents: `cp -r source/ target/` 
* To rename a single file just use `mv`!
* Printing a file line by line: `cat [file] | more` 
* Printing the first few lines of a file: `head [file]` or `head [file] -n [number of lines]`

### npm

* Checking which version of npm is running: `npm -v`
* Going back to a previous version of npm *(for example npm 5)*: `npm install -g npm@5`

### Git

* Comparing the last two commits: `git diff HEAD^ HEAD`
* Limiting the diff to one file: `git diff HEAD^ HEAD -- [filename]`
* Specifying the number of lines to show around each diff: `git diff HEAD^ HEAD -U[# of lines]`
* Ignoring a file (like package-lock.json) from a git diff: `git diff HEAD^ HEAD -- . ":(exclude)package-lock.json"`
* Reverting a single file to the last commit: `git checkout [filename]`
* Fetch + rebase: `git fetch --all && git rebase -v`
* Adding a remote origin: `git remote add origin [url]`
* Listing all branches: `git branch -r`
* Listing all branches starting with the ones with the most recent commits: `git branch --sort=-committerdate`
* Deleting a branch locally: `git branch -d [branch]`
* Removing a remote branch (be careful!!): `git push origin --delete [branch]` 
* Copying the content of a branch to a new one: `git checkout -b new_branch old_branch`
* Going back to head while saving local modifications: `git stash`
* Undoing a `git stash` with: `git stash pop`
* Merging two branches: `git checkout` the branch you want to merge to, then `git merge [branch to copy from]`
* Undoing the last commit ONLY if not pushed yet. Your changes will still be kept in the filesystem: `git reset HEAD@{1}`


### Javascript Debugging

* Using `console.group("Group name")`, logging... and then `console.groupEnd()`
* A convenient way to print objects is `console.dir(object, { depth: null })`



### Flow

* Ignore an error on the next line with: `// $FlowFixMe`
* Doing an enum in Flow: `"success" | "fail"`
* Enum as object keys: `{ ["success" | "fail"]: true }`
* Object examples:
  * `{ [string]: Array<string> }` 

### Eslint

* Ignoring a rule in a file (for example max-lines): `/* eslint max-lines: 1 */`
* Ignoring an error in the next line: `/* eslint-disable-next-line id-length */`
* Disabling eslint for the whole file: `/* eslint-disable */`


### Kaggle CLI

* Configuring the CLI: `kg config -g -u [username] -p [password] -c [competition]`
* Downloading competition data: `kg download`

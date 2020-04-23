# TIL

### Ubuntu (or more generally, Linux)

* Checking the current linux kernel version: `uname -r`
* Checking out which  distribution and version of linux you're running: `cat /etc/issue`
* Display shared dependencies of a binary: `ldd [binary]`
* Running a command (or interactive shell) with a special root directory: `chroot [new root] [command]`


### Bash

* Removing a directory and its contents: `rm -rf [dirname]`
* Moving a directory and its contents: `mv source/ target/`
* Copying a directory and its contents: `cp -r source/ target/` 
* To rename a single file just use `mv`!
* Printing a message to the console: `echo “[my message]”`
* Writing to a text file: `echo “[my message]” > [my .txt file]`
* Printing a file line by line: `cat [file] | more` 
* Printing the first few lines of a file: `head [file]` or `head [file] -n [number of lines]`
* Writing stdout and stderr outputs to a file: `[command that generates output] &> [filename.txt]`
* finding files by name in the current directory: `find . -name [filename]`
* finding files by name in a directory, with depth: `find [directory] -name [filename]`
* finding files by name in a directory: `find [directory] -maxdepth [depth] -name [*filename*] -print`
* searching files for a string or regex: `grep '[regex]' [directory] -rnw`
* searching files for a string (additional options): `grep '[regex]' [directory] -rnw -A [# of lines to show before match] -B [# of line after]`

#### scripts
* Printing a variable: `echo "$variable"`
* Storing the output of a command in a variable : `variable="$(command)"`
* Parsing JSON with bash: check the jq tool `https://stedolan.github.io/jq/` !

#### processes
* Listing all running processes: `ps aux`
* Listing open node files and their processes: `lsof -i | grep node`
* Searching for a process that matches a string: `ps aux | grep [search string]`
* Killing a process: `kill [process ID]`
* Killing all processes which match a name: `pkill [name]`
* Getting the name of the command that created a process: `ps -o comm= -p [PID]` 
* Getting some info on a process: ` ps -Flww -p [PID]`

### Node

#### npm

* Checking which version of npm is running: `npm -v`
* Going back to a previous version of npm *(for example npm 5)*: `npm install -g npm@5`
* Listing all globally installed modules: `npm ls -g --depth 0`

#### nvm
* Listing installed Node versions: `nvm ls`
* Using one of the installed Node versions: `nvm use [version]`
* Updating and managing multiple versions of Node: check `https://github.com/creationix/nvm`

#### Paths and Dirs
* Getting the path of the current directory: `const DIR_PATH = path.resolve(__dirname);`
* Going from a relative to an absolute path: `path.resolve(DIR_PATH, '../../relative/path')`

### Git

* Comparing the last two commits: `git diff HEAD^ HEAD`
* Comparing the last two commits and only showing changed filenames: `git diff HEAD^ HEAD --name-only`
* Comparing the last commit with the staged differences: `git diff --cached`
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
* Untracking a file that has already been commited, after adding it to .gitignore: `git rm --cached [filename]`


### Docker

* Displaying system-wide info: `docker info`
* Displaying docker version: `docker -v`


### PostgreSQL

* Checking which version is running: `postgres -V`

## SQL
* [SQL](./sql.md)

### Selection

Here is the format of a select statement: `SELECT column or columns FROM tablename WHERE optional conditions`

* selecting all columns of all rows of a table: `SELECT * from [tablename]`
* selecting all columns of all rows where [column] starts with some [characters]: `SELECT * from [tablename] WHERE [column] LIKE '[characters]%'`
* selecting all columns of all rows where [column] contains some [characters]: `SELECT * from [tablename] WHERE [column] LIKE '%[characters]%'`
* selecting all columns of all rows where [column] ends with some [characters]: `SELECT * from [tablename] WHERE [column] LIKE '*[characters]'`

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


### MongoDB Shell

* Launching the mongo shell : `mongo`
* Show database currently in use: `db`
* Showing all databases: `show dbs`
* Switching databases: `use [database]`

### Conda

If running a Jupyter Notebook, be sure to run the following commands from within the Jupyter terminal

* Checking Conda version: `conda -V`
* Updating Conda package: `conda update [package]`
* Checking the list of all Conda packages: `conda list`
* Upgrading Conda version: `conda update conda` and then `conda update anaconda` to update Anaconda packages

### Jupyter

* Checking Jupyter version: `jupyter notebook --version`
* Upgrading Jupyter if using Anaconda: `conda update jupyter`

### AWS

#### AWS CLI
(PS: These commands are not guaranteed to be up to date, but I just put them here to find them easily

* Listing the ECS tasks of a cluster: `aws ecs list-tasks --cluster [cluster]`
* Describing an ECS task: `aws ecs describe-tasks --cluster [cluster] --tasks [task ID or list of IDs separated by a space]`


#### Cloudwatch Insights

* Basic query: Fetch the 20 most recent logs
```
fields @timestamp, @message
| sort @timestamp desc
| limit 20
```

* Basic query: Fetch the 20 most recent logs that contain a certain pattern ("error:")
```
filter @message like "error:"
| sort @timestamp desc
| limit 20
```

* Basic query: Fetch the 20 most recent logs the pattern A or B
```
filter @message like "A" or @message like "B"
| sort @timestamp desc
| limit 20
```

* Basic query: Fetch the 20 most recent logs that match a regex or contain a special character ("#500")
```
fields @timestamp, @message
| filter @message like /#500/
| sort @timestamp desc
| limit 20
```


# Command cheatsheat

## Ubuntu terminal

Use | Command | Description
---------|----------|---------
 Change directory | `cd path/to/dir` | Lets you browse the directory tree 
 Copy file | `cp path/to/copy/file path/to/destination/` | Copies a file
 Copy directory | `cp -R path/to/copy/directory path/to/destination/` | Copies a directory to a different location
 Move a file or directory | `mv path/to/source path/to/destination` | Moves a file or folder. Only real way to rename something in a terminal 
 Delete (Remove) | `rm path/to/delete` | Removes files Can remove lots of stuff at once
 Delete (Remove) directories | `rm -rf path/to/delete` | Removes files, folders recursively 
 Read end of file | `tail path/to/file` | Reads the last n (dedault 10) lines.
 Read entries in realtime | `tail -f path/to/file` | Reads the last n lines but prints every new line that is created
 Install stuff | `apt install package-name` | Installs a package from Ubuntu repositories
 Delete stuff | `apt remove package-name` | Removes a package from Ubuntu repositories
 Change file permissions | `chmod <permisions> path/to/file` | Changes permission of file or folder. Can use number [calculator](http://permissions-calculator.org/) or + and -

### Special characters

### Piping and redirection (https://ryanstutorials.net/linuxtutorial/piping.php)

#### > (redirection)

##### Purpose

Write output of command before `>` to file after `>`, overwriting the contents of the file 

##### Example
A file called `howdy.txt` has some content

```
cat howdy.txt
    original text!
```

If you echo a line and use > to pipe the output to the file

`echo "Howdy" > howdy.txt`

It will be overwritten by the output of the first command:

```
cat howdy.txt
    Howdy
```

#### >> (redirection, but append)

##### Purpose

Append output of command before `>` to file after `>`, adding to the contents of the file

##### Example
A file called `howdy.txt` has some content

```
cat howdy.txt
    original text!
```

If you echo a line and use > to pipe the output to the file

`echo "Howdy" >> howdy.txt`

It will be overwritten by the output of the first command:

```
cat howdy.txt
    original text!
    Howdy
```

#### | (pipe)

##### Purpose

Connect the standard output of command before the pipe `|` to the standard input for command after the pipe `|`

##### Example

A file called `howdy.txt` has some content

```
cat howdy.txt
    Howdy 1
    Howdy 2
    Howdy 3
    Howdy 4
    Howdy 5
```

By cat-ing the file (showing contents to standard output) and piping to tail -n 3 (showing the last three lines), we can display only the last lines of the output of the cat command. 

```
cat howdy.txt | tail -n 3
    Howdy 3
    Howdy 4
    Howdy 5
```

This example is useless, since tail does the same, but you get the general idea. 


### Paths


Meaning | Shorthand | Description
---------|----------|---------
Root  | `/` | If path starts with `/` it will look for the path starting from the first directory in the filesystem
Current | `.` | A "folder" that points to the directory it is called in. Used to specify that a path starts from the current dir
Previous | `..` | A "Folder" that points to the previous directory. Used to go back one level to search for something
Home | `~` | An easier way to "go home". This will always take you to `/home/yourusername/`

## Terms

Term | Description | Example 
---------|----------|---------
 Absolute path | Starting from ROOT  | `tail -f /var/log/syslog` is an absolute path 
 Relative path  | Starting from CURRENT DIR | If I am in `/var/log/apache2` but I need to read `/var/log/syslog` :`tail -f ../syslog`
 Dir | Directory, Folder | 
 Webroot | Start path of a website | `/var/www/myproject` could be the webroot of the site myproject.something.com

## Git commands

Action | Command | Notes
---------|----------|---------
 Add new element | `git add path/to/file` | if path is `.` every new file will be added
 Create a commit | `git commit -a -m "Add commit message"` | -a parameter adds every change to the commit. 
 Upload (push) commited changes to source  | `git push` | the source of the code is configured in the `.git` directory
 Download (pull) latest changes from source | `git pull` | Don't forget to pull latest code before trying to push your changes
 Change active branch | `git checkout branchname` | meow meow
 Download a new project (clone) | `git clone git@github.com:maristitovs/ravenclaw.git` | substitute the address part with the project you wish to clone

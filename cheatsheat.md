# Command cheatsheat

## Ubuntu terminal

Use | Command | Description
---------|----------|---------
 Change directory | `cd path/to/dir` | Lets you browse the directory tree 
 Delete (Remove) | `rm path/to/delete` | Removes files Can remove lots of stuff at once
 Delete (Remove) directories | `rm -rf path/to/delete` | Removes files, folders recursively 
 Read end of file | `tail path/to/file` | Reads the last n (dedault 10) lines.
 Read entries in realtime | `tail -f path/to/file` | Reads the last n lines but prints every new line that is created
 Install stuff | `apt install package-name` | Installs a package from Ubuntu repositories
 Delete stuff | `apt remove package-name` | Removes a package from Ubuntu repositories
 Change file permissions | `chmod <permisions> path/to/file` | Changes permission of file or folder. Can use number [calculator](http://permissions-calculator.org/) or + and -


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

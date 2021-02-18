# Ethical Hacking Cheat Sheet

Someone should find this useful!

## Basic Linux Commands

### User Management

```markdown
- useradd --- add user
- userdel --- delete user and related files
- usermod --- modify suser account
- addgroup --- add an user group
- delgroup --- delete an user group
- passwd --- change an user's password
- su <user, default is root> --command --- execute command as another user
```

### Process Management

```markdown
- ps -aux --- view info about all processes
- systemctl list-units --type=service --- view info about all services
- journalctl -u <service> --no-pager --- view logs for the specified service
- kill <signal> <pid> --- sends the signal to the specified pid (see signal list below)
- jobs --- view background processes activated by the user
- bg --- keeps a process running in the background, can also use the & sign at the end of the command
- fg --- move a process to the foreground
```
**NOTE:** the `screen` utility can also be used to run jobs in the background, can be installed via apt or other package managers

### Kill Signals

```markdown
- 1 (SIGHUP) --- signal sent when terminal is closed
- 2 (SIGINT) --- signal sent when CTRL+C is pressed (tells the process to finish up)
- 3 (SIGQUIT) --- signal sent when CTRL+D is pressed (tells the process to quit)
- 9 (SIGKILL) --- kills the process, no cleanup operations
- 15 (SIGTERM) --- terminate the process
- 19 (SIGSTOP) --- stop the process, usually because the system can't handle it
- 20 (SIGSTP) --- signal sent when CTRL+Z is pressed (suspend process for the user to handle)
```

### "find" Command

**Usage (phrases in italics are arguments that should be specified, while bold is required)**

find **pwd** -type **see below** -name **desired file name** -user *owner of file* -size *see below* -newermt *date: yyyy-mm-dd* -exec ls -al {} \; 2>/dev/null	

**-type** argument: Can either be **d** for directory, or **f** for file
*-size* argument: Follows this structure:
`(+ [greater than] or - [less than])(file size, ends in g (gigabyte), m (megabyte), or k (kilobyte))` ex -size +50k OR -size -75m

**EXAMPLE:** `find / -type f -name *.conf -user root -size +20k -newermt 2020-03-03 -exec ls -al {} \; 2>/dev/null`



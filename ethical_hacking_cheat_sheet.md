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
```

### Kill signals

```markdown
- **1 (SIGHUP)** --- signal sent when terminal is closed
- **2 (SIGINT)** --- signal sent when **CTRL+C** is pressed
```

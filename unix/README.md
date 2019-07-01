[Back](../README.md)

# Unix questions

## How to check if port 80 taken

``sudo lsof -i tcp:80``

result:

```
COMMAND  PID   USER   FD   TYPE             DEVICE SIZE/OFF NODE NAME
java    6699 rustam   81u  IPv6 0xdb2c7da1a910fdd7      0t0  TCP *:80 (LISTEN)
```


## How to view log file

less

| COMMAND | DESCRIPTION |
| :------ | :---------- |
| g  <  ESC-<      | Go to first line in file (or line N).         |
| G  >  ESC->      | Go to last line in file (or line N).          |
| /pattern         | Search forward for (N-th) matching line.      |
| ?pattern         | Search backward for (N-th) matching line.     |
| n                | Repeat previous search (for N-th occurrence). |
| N                | Repeat previous search in reverse direction.  |
| q  :q  Q  :Q  ZZ | Exit.                                         |

### In real time

``tail -f log_name``

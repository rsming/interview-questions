[Back](../README.md)

# Unix questions

## How to check if port 80 taken

``sudo netstat -tulpn | grep :80``

result:

``tcp6       0      0 :::80                   :::*                    LISTEN      3865/java``


## How to view log file

less

| COMMAND | DESCRIPTION |
| :------ | :---------- |
| g  <  ESC-< | Go to first line in file (or line N).         |
| G  >  ESC-> | Go to last line in file (or line N).          |
| /pattern    | Search forward for (N-th) matching line.      |
| ?pattern    | Search backward for (N-th) matching line.     |
| n           | Repeat previous search (for N-th occurrence). |
| N           | Repeat previous search in reverse direction.  |

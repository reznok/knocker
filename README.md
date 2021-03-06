# knocker
Python 3 utility to help with CTF or boot2root challenges that involve port knocking.

Requires root or sudo privileges.
Requires argparse.
```
pip install argparse
``` 

```
# ./knocker.py -h
usage: knocker.py [-h] [-c CLOAKED] [-m MAXLEN] (-b | -r RANGE | -p PORTS)
                  dest_ip

Tool to interact with ports cloaked with port knocking. Specify -p, -r, or -b,
and a target IP. -c can be used for success checking if the cloaked port is
known. Requires root or sudo privileges for socket creation.

positional arguments:
  dest_ip               Target host IP that makes use of port knocking

optional arguments:
  -h, --help            show this help message and exit
  -c CLOAKED, --cloaked CLOAKED
                        Specify the target cloaked port for success checking
  -m MAXLEN, --maxlen MAXLEN
                        Specify the max iterations a brute force will run
                        before assuming failure (default 10)
  -b, --bruteforce      Have knocker automatically brute force the target for
                        you. Shortcut for -r 1-65535
  -r RANGE, --range RANGE
                        Specify a suspected range of ports to attempt to brute
                        force (i.e. 1000-1200)
  -p PORTS, --ports PORTS
                        Comma separated list of ports to knock (in proper
                        order)
```

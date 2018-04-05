# SSH Colorize

Add a file: /etc/profile.d/colorenv.sh

For staging (default text will be green):
```
export LS_COLORS="$LS_COLORS:no=32:ex=32;1:"
export PS1='\[\e[0;32m\][\u@\h \W]\$ '
```

For production (default text will be red):
```
export LS_COLORS="$LS_COLORS:no=31:ex=32;1:"
export PS1='\[\e[0;31m\][\u@\h \W]\$ '
```

# MySQL
Each application and administrator should have different username for database access. Therefore it's easy to spot which one made a query when things go wrong.

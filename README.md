SaltStack git hook
==================

If you keep your saltstack states and pillars in git (for example, gitolite)
It's usefull if you can see test salt call in git push log

Installation
------------

Add this post-update hook to your git repository on saltmaster sarver
For example, if you use gitolite, put post-update script to directory:

/home/gitolite/repositories/SALTSTACK-REPO-NAME/hooks

Usage
-----

On local pc, when you push changes to salt, name you branch as
MINIONBANE-STATENAME
and you'll see result of command
```
salt 'MINIONNAME*' state.sls STATENAME test=True
```

Example
-------
```
$ git push origin master:myserver-mystate
...
salt 'myserver*' state.sls mystate test=True
...

$ git push origin master:myserver
...
salt 'myserver*' state.highstate test=True
```

## HG -> GIT Bridge for Coopengo repositories

Some utilities to synchronize Coopengo Git Clones from Tryton HG official repositories.

**NB: all git and hg repositories inside the bridge should never be used for dev/patch**

### New Bridge environment

To create a new Bridge environment (you should be a Coopengo Github member)

```
git clone git@github.com:coopengo/bridge.git
cd bridge
git submodule init
git submodule update
./init
```

### Sync Git Repos

To synchronize a set of repositories

```
./sync <repo-1> <repo-2>
```

To synchronize all repositories

```
./sync
```

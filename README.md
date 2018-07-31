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

### Checkout to appropriate branch

Unless you are synchronizing Tryton repositories with Coog on master, checkout to the appropriate bridge branch

```
git checkout coog-<version>
```
This is very important, otherwise unwanted modules will be added.

### Sync Git Repos

To synchronize a set of repositories

```
./sync <repo-1> <repo-2>
```

To synchronize all repositories

```
./sync
```

### Merge Branches

The synchronized branches now need to be merged. It is possible to run `sync-tryton` to merge the branches
but you must handle conflicts manually.

```
./sync-tryton <repo>
```

## Documentation

- [Add a new tryton repository to trytond-modules](doc/add_repo_trytond_modules.md)

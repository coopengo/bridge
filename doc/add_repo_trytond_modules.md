In order to add a new Tryton HG official repository <new_repository> to trytond-modules, follow the following steps

- Create a <new_repository> repository in Coopengo using Github. This step requires specific authorizations, you may ask someone having them to do it. This repository should not contain any file or any commit.

- In a clean environment, clone bridge repository
```
git clone git@github.com:coopengo/bridge.git
cd bridge
git submodule init
git submodule update
./init
```
- Clone <new_repository> in hg
```
cd hg
hg clone http://hg.tryton.org/modules/<new_repository>
```
- Create <new_repository> in git
```
cd ../git
mkdir <new_repository>
```
- Connect to git
```
cd <new_repository>
git init
git remote add origin git@github.com:coopengo/<new_repository>.git
```
- Open bridge/modules file in your editor, and add <new_repository> to the modules list
- Open bridge/branches file in your editor, and check all branches you want synchronized are available in the branches list, otherwise, add branches to synchronize
- Launch the following command
```
cd ..
./sync <new_repository>
```
- In your environement, go to trytond-modules repository
```
cd modules
git submodule add git@github.com:coopengo/<new_repository>.git
```
- Check <new_repository> has been added to the modules list, that it is in the appropriate branch and commit tag
- Check <new_repository> has been added to trytond-modules/.gitmodules file
- Commit and push in trytond-modules

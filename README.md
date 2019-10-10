## Node Note

> This is a block

> git submodule add [submodule's git url]

> super project only knows that submodule has changed
> not the detail
>
> commit submodule first then push it to github then commit super and push it ...

1. Delete the relevant section from the .gitmodules file.
2. Stage the `.gitmodules` changes:
   > git add .gitmodules
3. Delete the relevant section from `.git/config`.
4. Remove the submodule files from the working tree and index:
   > git rm --cached path_to_submodule (no trailing slash).
5. Remove the submodule's `.git` directory:
   > rm -rf .git/modules/path_to_submodule
6. Commit the changes:
   > git commit -m "Removed submodule <name>"
7. Delete the now untracked submodule files:
   > rm -rf path_to_submodule

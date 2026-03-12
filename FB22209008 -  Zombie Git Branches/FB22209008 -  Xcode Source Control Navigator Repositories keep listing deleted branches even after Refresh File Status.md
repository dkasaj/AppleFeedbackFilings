# Xcode Source Control Navigator Repositories keep listing deleted branches even after Refresh File Status

### Problem

Deleting a Git branch outside of Xcode (for example via the command line or another Git utility) does not remove it from the Source Control Navigator branch list until Xcode is restarted.

### Details / steps to reproduce:

1. Start by having a project with a Git repository (zombie-branches-1.png)
2. Create a new branch (zombie-branches-2.png)
3. See the new branch appear in Source Control Navigator > Repositories > Branches (zombie-branches-3.png)
4. Use command line or any Git utility to switch branches away from the branch created in this example, and delete the branch in question (zombie-branches-4.png)
5. Return to Xcode. It will correctly mark "current" branch. It will also list the just-deleted branch, and might also have it labeled as "current". (zombie-branches-5.png)
6. In the Integrate menu, click "Refresh File Status". This usually makes Xcode up-to-date with any repository changes. The deleted branch will still be there. (zombie-branches-6.png)
7. The only way to truly get rid of the deleted branch in this list is to restart Xcode.

### Expected behavior

Deleted branches should disappear from the Source Control Navigator after Refresh File Status without requiring an Xcode restart.
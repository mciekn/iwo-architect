# Updating the `.eap` file
In order to update the file we will have to do a little mumbo jumbo with the git index as it does not support 
tracking compressed files.

The basic idea is to 'record changes' by changing user privilages of the file.
So you run:
```
git update-index --chmod=-x IWO-LARP.eap
```
or:
```
git update-index --chmod=+x .\IWO-LARP.eap
```
whatever is in motion at the time, you can chceck if the `x` was added or removed in commit details in `GH` or `git` cli. 
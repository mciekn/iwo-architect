# Workflow
### Branch policy
It is forbidden by branch policy to push directly to main. In order to commit and merge new changes, please create separate branch based on main and merge it via pull request.
### Handling Enterprise Architect files
There are two ways of working on EA project:
* Work on single `.eap` file and commit it as described below
* To work paralelly, use XML files to import/export packages from/into `.eap` file.\
\
During work on certain task, please remember to update .eap file that contains whole enterprise architect project.
At the same time, please export package you are working on into an XML file, and commit it explicitly into this repo.
### Export / Import of EA Packages in XML
In order to import EA Package in XML format, select:

&nbsp;&nbsp;&nbsp;`Publish` > `Model Exchange` > `Import XML` > `Import Package from XML`\
&nbsp;&nbsp;&nbsp;or\
&nbsp;&nbsp;&nbsp;`Ctrl+Alt+I`

In order to export EA package in XML format,
1. Select package that you want to export in project tree
2. `Publish` > `Model Exchange` > `Import XML` > `Import Package from XML`\
or\
`Ctrl+Alt+E`


### Updating the `.eap` file
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
For example change: 
```
 BIN +70 KB (100%)  IWO-LARP.eap 100755 → 100644
```  
means that last option was -x so in another commit you will have to add '+x' option.

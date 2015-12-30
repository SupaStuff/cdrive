# cdrive
Bash script that provides a git like experience for Google Drive by using cURL
--
Inspired by [odeke-em/drive](https://github.com/odeke-em/drive)  
Should work on Unix, Mac, and Git for Windows.  
### TODO:  

``` $ cdrive init ```
> creates the directory .cdrive/

``` $ cdrive auth ```
> asks for user credentials and stores it in .cdrive/auth. Maybe just user name.

``` $ cdrive remote *remote_url* ```
> creates the file ./cdrive/remote containing the text *remote_url*

``` $ cdrive add [-r] *expression* ```
> expand the *expression* and append it to .cdrive/update with an add keyword on each line. If -r is passed, use find to expand, otherwise use ls.

``` $ cdrive rm [-r] *expression* ```
> expand the *expression* and append it to .cdrive/update with a del keyword on each line. If -r is passed, use find to expand, otherwise use ls.

``` $ cdrive pull ```
> First download .cdrive/tracker if it exists and then download and overwrite everything logged in .cdrive/tracker. If any of these exists locally, but not on google drive, remove it.  
>If .cdrive/tracker does not exists, try to use a local copy of .cdrive/tracker. If that also doesn't exist, download everything.

``` $ cdrive push ```
> get each line from .cdrive/update if it exists and apply each action to .cdrive/tracker. Delete .cdrive/update and upload all files that are listed in .cdrive/tracker along with .cdrive/tracker itself.

push and pull should only download and upload files with differing modification times.  
In the future, think about how to add an ignore file.

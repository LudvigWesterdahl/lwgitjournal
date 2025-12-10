# Install_script
# 3
When running install it will take lates version.
Install arg should take option -p PLATFORM like "arch" and act accordingly. I could make a platform like "mac" etc. See bash constans grok chat to find how to share the value for PLATFORM.

Arg: upgrade -v VERSION<br>
Fetch whatever file (curl) inspegt if needed and upgrade the program. However, when running main script it will do latest.

Alt 1) If version doesnt exist

sdkman: error version 2.3.7 does not exist

Alt 2) if version is not possible to get from remote or local

sdkman: current (2.0.3 or null) ignoring version 2.9.1 installing latest

sdkman: installed (2.7.6 or null)

Alt 3) all works

sdkman: current 2.0.3 installing 2.9.1

sdkman: installed 2.9.1


Arg: version

Check current version and check if newer exist. Also if possible print all available versions.

Alt 1) newer exist

sdkman: available versions 
```
sdkman: 1.9.7
sdkman: 1.9.8
sdkman: 2.0.1
sdkman: 2.2.4
sdkman: 2.3.1
sdkman: current 2.0.1 -> latest 2.3.1
```

Alt 2) have newest

sdkman: 2.0.1

Alt 3) cant find newest (error msg then report null latest)
```
sdkman: error curl ... timeout to remote x.y.z
sdkman: current 2.0.1 -> latest failed
```
Alt 4) version from remote or current is not possible to get

sdkman: current V or null -> latest V or null

# 2

boot-stuff on usb (ssh key and init sh file to put ssh file and fetch from github)

# 1
There should be a master script that calls all of them. If any program verify fails (returns non zero) then the script should not install anything. But it shouls log all that fails/succeeds. 

Folder programs contain one script for each.
If ran and already installed, just log it and exit successfully.

Each program script should have three args: verify, install, uninstall.

verify arg

should return 0 if can install or already installed. Or 1 if it cant install it for some reason (ssh key missing, no network connection etc) and log the failure.
sdkman: cant install no internet

install arg

If already installed it should log (not fail)
sdkman: already installed

But if installation fails it should not hide it... And instead call its uninstall.

uninstall arg

If not installed it should log (not fail)
sdkman: not installed

Ex:
- programs/_all.sh
- programs/sdkman.sh

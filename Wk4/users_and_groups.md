# Administering Users and Groups
- `/etc/passwd` - contains user config data
	+ format -  `name:password:UID:GID:GECOS:homedirectory:shell`
	    -  `name` - username
	    - password`=x if `/etc/shadow` is used
	    - UID - user id number
	    - GID - group id number
	    - GECOS - optional text description of user
    	    + General Electric Comprehensive Operating System
	    - homedirectory - `/home/username`
	    - shell - `/bin/bash`
- `/etc/shadow` - contains user password encrypted
    + format: `name:password:lastchange:min:max:warn:disable1:disable2`
        * lastchange - date of most recent password change
        * min - number days must wait to change password
        * max - number days before manditory change
        * warn - number of days before max to warn user to change password
        * disabled1 - number days account disabled after password expiration
        * disabled2 - number of days to disble account
- `/etc/group` - list all groups and their members
    + format - `name:password:GID:members`
        * name - group name
        * password - normally x, group passwords rarely used
        * GID - group id
        * members - comma separated list of member names
- `getent` - display contents of passwd,shadow,group
    + eg. `getent shadow`
    

## Creating users and groups
- `useradd` - add new user
- `/etc/default/useradd` - default user config
- `passwd username` - set password for username
- `usermod` - modify user account
- `chfn` - change user optional text description GECOS
- `change` - modify password expiration
- `chsh` - change users shell
- `userdel` - delete user
    + users files become owned by deleted users UID
    + `userdel -r` - deletes home directory and all file
- `groupadd` - add new group
- `groupmod` - modify group
- `groupdel` - delete group
- `groups` - list groups belonging to
- `id` - list UID, and GID for all groups belonging to
- `newgrp` - change users primary group
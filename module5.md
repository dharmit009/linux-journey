# Module 5.

## User Management:

Each user may has it's own home directory saved in `/home`
and it may vary in different distributions.

Whenever a user is created it creates its own `UID` and a
group with its own `GID`.

### What is a shadow file?

A shadow file contains password information for the system
and user account available on the local host and is password
placeholder for `/etc/passwd`

shadow file: `/etc/shadow`.

**Here are a few examples:**

1. root:$6$1oEz6jcxCG9k7IYt0rSpoivESKa.:18894::::::
1. hmm:$6$lziyl3amAlcJxNefEpLPdvdtAw6Q0:18894:0:99999:7:::

Let us break it down:

> root : MyEPTEa$6Nonsense : 15000 : 0 : 99999 : 7 : : :

1. Username : `root`
1. Encrypted passwd : `MyEPTEa$6Nonsense`
1. Date of passwd change : `15000`
1. Minimum passwd age : `0`
1. Maximum passwd Age: `99999`
1. Passwd Warning Period : `7`
1. Passwd inactivity period : `NULL`
1. Account Expiry Date : `NULL`
1. Reserved field for future: `NULL`

### What is a password file?

The password file stored in /etc folder stores a detailed 
information about the user like their login shell, username,
password hash, and much more as we will see in the example below.
passwd file: `/etc/passwd`.

**Here are a few examples:**

1. root: x :0:0::/root:/bin/bash
1. hmm: x :1000:1000:Hmm:/home/hmm:/bin/bash

Let us break it down:

> hmm : x : 1000 : 1000 : Hmm : /home/hmm : /bin/bash

1. Username: `root`
1. User's Passwd: `x` (masked with shadow file)
1. User Id:  `0`
1. Group Id: `0`
1. GECOS Field:  `NULL`
1. User's Home Directory:  `/root`
1. User's Shell:  `/bin/bash`

### What is group file? 

The group file stores all the details about group and with 
all the permissions provided to them. 

**Here are a few examples:**

1. root : x : 0 : root
1. test : x : 1000 :

Let us break this down: 

> root : x : 0 : root

1. Group Name: `root`
1. Group Passwd: `x or *` (to use sudo passwd by default).
1. GID: 0
1. Users In group: root

## Account Management Using CMD: 

$ sudo useradd bob
|--> Used to create a new user named bob.

$ sudo userdel bob
|--> Used to delete a user named bob.

$ sudo passwd bob
|--> Used to change passwd for a user named bob.


# Level 6 → 7
This task has some more specific properties. The file is going to be *anywhere* on the server. Hmm, so that means that we'll have to run a system-wide search query it seems. We'll need to feed in the properties listed: owned by `user bandit7`, owned by `group bandit6`, and it's `33 bytes` in size.

## Solution
In our previous level solution we used the `find` command with some parameters. We know the file size and the file's owned properties. I know that we can run a `find` query on using the filesize, but I don't yet know if we can feed in the owned properties. Let's take a look at the manual and see if there's any flags we can use. There seems to be a flag called `-group <gname>` which takes the name of the group as a parameter! Then there's also the `-user <uname>` flag which takes the user's name as a parameter. Let's compose a command and see if it works.

`find / -size 33c -user bandit7 -group bandit6` might do it, let's try. Hmm... If we run this command we get a bunch of "Permission Denied" errors. Let's try and see if there's any way to get rid of these. If we do a quick Google search we can find that we can append with `2>/dev/null` to get rid of these. Let's give that a shot. Okay! The new command, `find / -size 33c -user bandit7 -group bandit6 2>/dev/null`, gave us a single file to look for: `/var/lib/dpkg/info/bandit7.password`. What `2>/dev/null` does is it discards the error messages. It redirects them to `/dev/null`, where the system discards them.

Let's quickly `cat` the found file and get on with the next one!

The password we got is `HKBPTKQnIay4Fw76bEy8PVxKEDQRKTzs`.

## Sources
https://www.cyberciti.biz/faq/bash-find-exclude-all-permission-denied-messages/
https://overthewire.org/wargames/bandit/bandit7.html

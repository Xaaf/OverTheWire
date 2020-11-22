# Level 4 → 5
Hmm... This time we have the password stored in the only human-readable file in `inhere`. Let's do some digging!

## Solution
If we do a `ls` we can see that we got a total of 10 files. That'd not be too big of a deal to `cat` through them all, but trying to cat even the first one returns some error. Clearly those files aren't all meant to be read using `cat`. Let's take a look at the "Commands you may need to solve this level" section. There's a new command in there which we haven't used yet! Well, there's three but the first one we find is `file`. If we check the manual on `file` (`man file`) we can see that it can determine the file type! That might be useful. Let's mess around with it a bit. Let's try just feeding it one of the files as input... `file ./-file00` returns `./-file00: data`! That is very useful!

How do we easily check all files though? Well, for this we can just use a wildcard. Let's do `file ./-file*`. What this means is that we use the `file` command on every file in here starting with `-file`. Okay, the return we got is very useful. We can see that each file is of the type `data`, except for `-file07`, which is ASCII text! Let's try reading that one, maybe it contains the password. `cat ./-file07` returns the password we were looking for, awesome!

The password we got is `koReBOKuIDDepwhWk7jZC0RTdopnAYKh`.

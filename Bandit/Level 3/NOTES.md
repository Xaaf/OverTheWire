# Level 2 → 3
This time instead of a dash we got spaces. We can probably do something similar to the last challenge.

## Solution
Spaces in filenames are not an uncommon thing, so it's important to know how to deal with them. There's a few solutions for this issue. We can put the filepath in a string, so `cat 'spaces in this filename'`, or we can "escape" the spaces. What does this mean? Well, normally spaces are meant to distinguish the syntax for a command. By escaping these spaces with a `\` we can tell the computer to ignore the space for the syntax and use it for the path argument. We'd get something like `cat spaces\ in\ this\ filename`. 

In my opinion putting the path in a string is easier. It's less tedious, and at the time of writing this I'm not aware of any downsides to it! So, let's do `cat 'spaces in this filename'`, and find our password!

The password we got is `UmHadQclWmgdLOKQ3YNgjWxGoRMb5luK`.

## Sources
https://overthewire.org/wargames/bandit/bandit3.html

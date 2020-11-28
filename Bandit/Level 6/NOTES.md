# Level 5 → 6
This time we have some very specific properties for the file we're looking into. Let's see how we find all of them.

## Solution
Let's first `cd inhere/` so we're in the correct folder. Hmm... We got a load of directories here... Doing this one manually would definitely be a pain. We *could* do a `file` command on the files in these directories by running `file ./maybehere*/*`, but if we run this we find a very, very long list. And the worst thing is that this list doesn't even narrow our options down by too much. 

We got some other commands at our disposal though. The level description also recommends `du` and `find`. Let's quickly check their descriptions in the manual. `du` seems to estimate the file space usage. That's useful! We know that our file is only 1033 bytes, so that should maybe narrow it down. `find` searches for files in a directory hierarchy. Maybe there's a way we can combine these commands?

Looking back into the manual file for `find` we can see that under the **TESTS** section there's a `-executable` flag, which matches the files to executables. We could maybe use this flag and inverse it to *hide* all executables? Furthurmore we find the `-size` flag, which takes a number and then a suffix for the units. Our file would match a `-size 1033c` flag, since our file is 1033 bytes big. Then there's also the `-type` flag, which has a few type arguments. `-type f` seems to be the one we're looking for, let's assemble a full command to test this out.

Let's try `find ./ -type f -size 1033c ! -executable`. As you can see we combined all three arguments we found which could lead to a solution. Hey! It worked! We get a single file as a return value, `./maybehere07/.file2`. Let's `cat` that file and get our password!

The password we got is `DXjZPULLxYr17uwoI01bNLQbtFemEgo7`.

## Sources
https://overthewire.org/wargames/bandit/bandit6.html

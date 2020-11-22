# Level 3 → 4
For this level we have to find a hidden file stored in the `inhere` directory. Shouldn't be too hard to find using some `ls` magic!

## Solution
If we do a `ls` in the root we find the `inhere` folder. Let's `cd inhere/` to go in it. If we type `ls` now we can't find any files. According to the level description the file is hidden. If we use the `-a` flag on our `ls` command we can find all files, including hidden ones! `ls -a` shows us the existence of `.hidden`, so let's `cat` that file and get the password.

The password we got is `pIwrPrtPN36QITSp3EQaw936yaFoFgAB`.

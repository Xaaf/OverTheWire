# Level 1 → 2
We're starting to ramp up a bit in difficulty now! Next up we have to find out how to read a file with a dashed name. Shouldn't be too hard.

## Solution
Using `ls` shows us the file we're after. Hmmm, it's named `-`. That's not too big of an issue right? Maybe `cat -` will show the contents? Nope, doesn't seem to work. Let's try `cat '-'`. Nope, also not the solution. Aha! What about `cat ./-`? Yes! This gets us the content we're after!

The password we got is `CV1DtqXWVFXTvM2F0k09SHz0YwRINYA9`.

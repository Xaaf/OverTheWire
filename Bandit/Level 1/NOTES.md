# Level 0 → 1
This level we have to find a file called `readme` in the home directory. We need to use the password found there to log in with `bandit1`. Let's take a look!

## Solution
We should still be logged in on `bandit0`. If you're not, make sure to log in on it! We're going to be using this account to find the `readme` file mentioned in the instructions. If we do a simple directory listing command, `ls`, we'll see that we're already in the correct directory. Now all we need to do is find the password hidden in this file. We can easily read its contents by executing `cat readme`. This will return the password we needed!

The password we got is `boJ9jbbUNNfktd78OOpsqOltutMc3MY1`. We'll be needing this for the next one, so let's SSH into it in advance. (`ssh bandit1@bandit.labs.overthewire.org -p2220`, then enter the password!)

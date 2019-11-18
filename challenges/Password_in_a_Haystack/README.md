# Password in a Haystack

Just about every machine in the [Top500 list of supercomputers](https://www.top500.org/list/2019/06/) runs a Linux (or at least Unix-like) operating system. Familiarity with the operating system's built-in utilities, along with common shell commands are a must.

Among the most helpful commands to know well is `grep` (which stands for "Global Regular Expression Print"). It's a way to search based on some user-provided pattern. At its simplest, `grep` works like cmd+F/ctrl+F. However, where it really shines is the ability to match patterns of characters, not just characters themselves. (Read more about Regular Expressions [here](https://en.wikipedia.org/wiki/Regular_expression).)

This directory has 2 password-protected PDFs, and the challenge is to use `grep` to find the passwords that open them.

The three files

- haystack_00.txt
- haystack_01.txt
- haystack_02.txt

contain the hidden passwords, but it's up to you to find them! 

##### A word on relevancy to HPC...

You may be thinking *"What does this have to do with supercomputing?"*, and this is an understandable question. After all, you could do this challenge on your laptop! The purpose of this challenge is more about fluency in a Unix-like environment than it is about running computationally complex simulations. To be most productive in an HPC environment, it's invaluable to be comfortable with the fundamental tools, including `grep`. 

Research teams running on the world's largest and most powerful computers like Summit often work with data at the scale of many terabytes, or even petabytes (*much, much* more data than the three text files included here), and pre-/post-processing or filtering of information on this scale generally requires more than a simple regular expression match.
+++
title = "Bash"
date = 2020-06-06T19:09:02+02:00
weight = 5
+++

## Bash Commands

- `atom .` : Open current directory in Atom
- `code .` : Open current directory in Visual Studio Code 
- `code <directory>` : Open directory in Visual Studio Code
- `open <directory>` : Open directory in Finder
- `node (.*).js` : Run javascript file in bash

https://tecadmin.net/tutorial/bash-scripting/bash-command-arguments/

- `tail -f <log-file>`

### Grep

```bash
cat file.txt | grep "title"
```

## Bash Snippets

### For loop

```bash
#!/bin/sh

for x in dog elephant fish; do
	echo $x
done
```

### If-Else statement

```bash
#!/bin/sh

if [ $1 = hotdog ]; then
	echo "You typed hotdog"
else
	echo You did NOT type Hotdog
	echo it was '"'$1'"'
fi
```

### Bash commands

```bash
#!/bin/sh
#
# This program is going to be awesome

echo "Progam is starting..."
ls -la
```

## Links

[Bash Tutorial](https://www.taniarascia.com/how-to-create-and-use-bash-scripts/)

[Cheatsheet](https://devhints.io/bash)

[Full Handbook](https://www.freecodecamp.org/news/the-linux-commands-handbook/)

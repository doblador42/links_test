# links test
## This is a repository to test if links have the same effect between operating systems

## results:

### Linux:

- [ ] Soft links propagate on OS
- [ ] Hard links propagate on OS
 
### Windows 10:

- [ ] Soft links propagate on OS
- [ ] Hard links propagate on OS

### MacOS & BSD (bsd coreutils)

- [ ] Soft links propagate on OS
- [ ] Hard links propagate on OS


## Commands executed:

### Symbolic Links:
```bash
	for directory in {Client,Server}
		do ln -sfr original_symbolic_link/HelloClass.java "$directory"/src/main/java/gr/uop/;
	done;
```
### Hard Links:
```bash
	for directory in {Client,Server}
		do ln original_symbolic_link/GoodbyeClass.java "$directory"/src/main/java/gr/uop/;
	done;
```

	
## Why?
Git doesn't take inodes under consideration.
after the repository is freshly cloned, **inodes** are not the same 

# links test
## This is a repository to test if links have the same effect between operating systems

## results after a fresh cloning:

### Linux:

- [x] Soft links propagate on OS
- [ ] Hard links propagate on OS
 
### Windows 10:

- [x] Soft links propagate on OS
- [ ] Hard links propagate on OS

### MacOS & BSD (bsd coreutils)

- [x] Soft links propagate on OS
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
		do ln original_hard_link/GoodbyeClass.java "$directory"/src/main/java/gr/uop/;
	done;
```
### files at the start:
> ./original_symbolic_link/HelloClass.java:

``` java
package gr.uop;

public class HelloClass {
    public  static String speak(){
        return "hello! ";
    }
}
```
> ./original_hard_link/GoodbyeClass.java:

``` java
package gr.uop;

public class GoodbyeClass {
    public  static String speak(){
        return "goodbye ";
    }
}
```

![Before fresh cloning](./Before.png)

### files after editing:
> ./original_symbolic_link/HelloClass.java (Soft Linked):

``` java
package gr.uop;

public class HelloClass {
    public  static String speak(){
        return "what else? ";
    }
}
```
> ./original_hard_link/GoodbyeClass.java (Hard Linked):

``` java
package gr.uop;

public class GoodbyeClass {
    public  static String speak(){
        return "42 is the Answer to the Ultimate Question of Life, the Universe, and Everything ";
    }
}
```

![After fresh cloning](./After.png)

So in conclusion hard links from the filesystem are treated as normal files from git


	
## Why?
Git doesn't take inodes under consideration.
after the repository is freshly cloned, **inodes** are not the same 


---

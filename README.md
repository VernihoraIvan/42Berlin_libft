# Libft - @42Born2Code

My implementation of some of the Standard C Library functions including some additional ones.

### TOC

- [What is libft?](#what-is-libft)
- [What's in it?](#whats-in-it)
- [How does it work?](#how-does-it-work)
- [How do I use the library?](#how-do-i-use-the-library)
- [How do I test it? How do I test my own implementations?](#how-do-i-test-it-how-do-i-test-my-own-implementations)
  - [To test the code in this repo](#1-to-test-the-code-in-this-repo)

### What is libft?

[Libft][1] is an individual project at [42][2] that requires us to re-create some standard C library functions including some additional ones that can be used later to build a library of useful functions for the rest of the program.

Disclaimer: _Reinventing the wheel is bad, 42 makes us do this just so we can have a deeper understanding of data structures and basic algorithms. At 42 we're not allowed to use some standard libraries on our projects, so we have to keep growing this library with our own functions as we go farther in the program._

### What's in it?

As you can see from the [Project instructions][1], there are 4 sections:

1.  **Libc Functions:** Some of the standard C functions
2.  **Additional functions:** Functions 42 deems will be useful for later projects
3.  **Bonus Functions:** Functions 42 deems will be useful for linked list manipulation

| Libc functions | Additional functions | Bonus Functions |
| :------------- | :------------------: | :-------------: |
| memset         |     ft_memalloc      |    ft_lstnew    |
| bzero          |      ft_memdel       |  ft_lstdelone   |
| memcpy         |      ft_strnew       |    ft_lstdel    |
| memccpy        |      ft_strdel       |    ft_lstadd    |
| memmove        |      ft_strclr       |   ft_lstiter    |
| memchr         |      ft_striter      |    ft_lstmap    |
| memcmp         |     ft_striteri      |                 |
| strlen         |      ft_strmap       |                 |
| strdup         |      ft_strmapi      |                 |
| strcpy         |      ft_strequ       |                 |
| strncpy        |      ft_strnequ      |                 |
| strcat         |      ft_strsub       |                 |
| strlcat        |      ft_strjoin      |                 |
| strchr         |      ft_strtrim      |                 |
| strrchr        |     ft_strsplit      |                 |
| strstr         |       ft_itoa        |                 |
| strnstr        |      ft_putchar      |                 |
| strcmp         |      ft_putstr       |                 |
| strncmp        |      ft_putendl      |                 |
| atoi           |      ft_putnbr       |                 |
| isalpha        |    ft_putchar_fd     |                 |
| isdigit        |     ft_putstr_fd     |                 |
| isalnum        |    ft_putendl_fd     |                 |
| isascii        |     ft_putnbr_fd     |                 |
| isprint        |                      |                 |
| toupper        |                      |                 |
| tolower        |                      |                 |

Notes:

- Most of the the files and function names are namespaced with an **ft** in front. It stands for Fourty Two
- The project instructions require that we put all the source files in the root directory but for the sake of this Github repo, I separate them into sub folders.

My code is not the best, but it passed all the 42 tests successfully.

### How does it work?

The goal is to create a library called libft.a from the source files so I can later use that library from other projects at 42.

To create that library, after downloading/cloning this project, **cd** into the project, copy all the files from the sub folders to the root directory and finally, call make:

    git clone https://github.com/VernihoraIvan/42Berlin_libft
    cd libft
    make

You should see a _libft.a_ file and some object files (.o).

Now to clean up (removing the .o files and the .c files from the root), call `make clean`

**WARNING:** `make clean` will delete all your files from your root directory. Do not run it if you're using the `Makefile` file. This is why I added the `Makefile-sample` file.

### How do I use the library?

I added an example file called **example.c**, it's using the function **ft_putstr** to print "DON'T PANIC" to the screen.

If you try to compile it with gcc using `gcc example.c` you will get an _undefined symbol_ error for ft_putstr.

You have to tell the file where your library resides and which library it is using:

`gcc example.c -L. -lft`

-L takes the path to your library. `.` in this case<br>
-l takes the name of your library. This is the set of characters that come after `lib` in your library name.

That's it. Now run it using `./a.out`

### How do I test it? How do I test my own implementations?

To test the code we're going to be using @alelievr's [Libft Unit Test][4]. There are [some][5] [good][6] [others][7] but I'll only be covering this one.

#### 1. To test the code in this repo

1.  Clone this repo and cd into it, make sure it's called `libft`:
    git clone https://github.com/VernihoraIvan/42Berlin_libft
    cd libft/

2.  Run Make so you can build the library:
    make
3.  Go back to the root directory and download @alelievr's Libft Unit Test:
    cd ..
    git clone https://github.com/alelievr/libft-unit-test

4.  Go into the test folder and run the test:
    cd libft-unit-test/
    make f

If you did everything correctly you should get a cool list of tests showing you the function names and if they passed or not.

# Lab Report 3 

## Researching Commands: The 'find' command

The 'find' command is a command line utility that is used to go through a file hierarchy. It helps users find files and directories, allowing them to perform other operations on them as they search through by file, folder, name, dates, owner, etc. In this report, we will be going over four 'find' command-line options that are used to navigate and search through a file

## -name 
Sources:
* ChatGPT-Searched `What are some find command-line options and what does each one do?`
* [Linux find command] https://www.computerhope.com/unix/ufind.htm


Using the  `find -name` option allows for the user to search for a file with a specifc name. For example `find path/directory -name "cse15l.txt"` will search for a file named `cse15l.txt` from the path/directory you are searching in. Here are some examples:

The `find -name` command is being used to search through the `written_2/` directory to find subdirectories that include files with the name `ch1.txt`. This is useful as users are able to search from the current directory and find all subdirectories that include certain files they're looking for, without having to manually go through each directory and searching through individual files. 
```
find written_2/ -name "ch1.txt"

written_2//non-fiction/OUP/Berk/ch1.txt
written_2//non-fiction/OUP/Abernathy/ch1.txt
written_2//non-fiction/OUP/Rybczynski/ch1.txt
written_2//non-fiction/OUP/Kauffman/ch1.txt
written_2//non-fiction/OUP/Fletcher/ch1.txt
```

In this example, the `find -name` command is being used to search through the same directory find all other subdirectories that have files with the pattern `*.txt` or all files ending in ".txt". This command is useful as it can help the user search for specific types of files in directories, like `PNG`, `PDF`, `DOC`, or `JPEG`. 
```
find written_2/ -name "*.txt"

written_2//non-fiction/OUP/Berk/ch2.txt
written_2//non-fiction/OUP/Berk/ch1.txt
written_2//non-fiction/OUP/Berk/CH4.txt
written_2//non-fiction/OUP/Berk/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch2.txt
written_2//non-fiction/OUP/Abernathy/ch3.txt
written_2//non-fiction/OUP/Abernathy/ch1.txt
written_2//non-fiction/OUP/Abernathy/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch6.txt
written_2//non-fiction/OUP/Abernathy/ch8.txt
written_2//non-fiction/OUP/Abernathy/ch9.txt
written_2//non-fiction/OUP/Abernathy/ch15.txt
written_2//non-fiction/OUP/Abernathy/ch14.txt
written_2//non-fiction/OUP/Rybczynski/ch2.txt
written_2//non-fiction/OUP/Rybczynski/ch3.txt
written_2//non-fiction/OUP/Rybczynski/ch1.txt
...
```

## -type
Sources:
* ChatGPT-Searched `What are some find command-line options and what does each one do?`
* [Linux find command] https://www.computerhope.com/unix/ufind.htm

Using the  `find -type` option allows for the user to search for a file of a specifc type. The three types that can be looked for is `f` for regular files, `d` for directories, and `l` for symbolic links. Here are the examples:

What the command `find written_2/ -type f -name "*.txt"` does is goe through all the directories from `written_2/` and searches for regular files `f` with the pattern name `.txt` in all the subdirectories. The command displays all the regular files of all the subdirectories that end with `.txt`. This is helpful for users to search through directories to find a specific type within files, looking for other directories or the files they contain.
```
find written_2/ -type f -name "*.txt"

written_2//non-fiction/OUP/Berk/ch2.txt
written_2//non-fiction/OUP/Berk/ch1.txt
written_2//non-fiction/OUP/Berk/CH4.txt
written_2//non-fiction/OUP/Berk/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch2.txt
written_2//non-fiction/OUP/Abernathy/ch3.txt
written_2//non-fiction/OUP/Abernathy/ch1.txt
written_2//non-fiction/OUP/Abernathy/ch7.txt
written_2//non-fiction/OUP/Abernathy/ch6.txt
written_2//non-fiction/OUP/Abernathy/ch8.txt
written_2//non-fiction/OUP/Abernathy/ch9.txt
written_2//non-fiction/OUP/Abernathy/ch15.txt
written_2//non-fiction/OUP/Abernathy/ch14.txt
...
```

In this example, the find command goes through the `written_2/` directory and searches for its subdirectories using the `-name` command, finding only two subdirectories witin the directory, `travel_guides1` and `non-fiction`. This is a helpful command with using of type `d` that can locate many directories and subdirectories.
```
find written_2/ -type d -name "travel_guides" 

written_2//travel_guides

find written_2/ -type d -name "non-fiction"

written_2//non-fiction
```

## -mtime
Sources:
* ChatGPT-Searched `What are some find command-line options and what does each one do?`
* [Linux find command] https://www.computerhope.com/unix/ufind.htm


The `find -mtime` command option allows the user to search for files that were modified under a specific time period. For example, `find path/directory -mtime -7` would search files in the path or directory that have been modified within the last 7 days. 

In this example, the command `find written_2/ -mtime -7 -type f` goes through the `written_2/` directory and searches for regular files (-type `f`) that have been modified in the last 7 days. The command found the `grep.txt` file in the directory which was modified in the past 7 days. This can be a useful command for the user to determine if certain files and directories have been recently modified under a certain time period or possibly identify files that haven't been modified. 
```
find written_2/ -mtime -7 -type f 

written_2//grep.txt
```

Like the example above, the `find written_2/ -mtime -10 -type d` goes through the same directory, but this time searches for directories (type `d`) that have been modified in the last 10 days. Below shows the directories and subdirectories that have been modified in the last 10 days. Using the `mtime` with the `-type` command option can be useful in finding specific types of files that have been modified, allowing the user to identify files where changes have been made.
```
find written_2/ -mtime -10 -type d

written_2/
written_2//non-fiction
written_2//non-fiction/OUP
written_2//non-fiction/OUP/Berk
written_2//non-fiction/OUP/Abernathy
written_2//non-fiction/OUP/Rybczynski
written_2//non-fiction/OUP/Kauffman
written_2//non-fiction/OUP/Fletcher
written_2//non-fiction/OUP/Castro
written_2//travel_guides
written_2//travel_guides/berlitz1
written_2//travel_guides/berlitz2
```

## -empty
Sources:
* ChatGPT-Searched `What are some find command-line options and what does each one do?`
* [Linux find command] https://www.computerhope.com/unix/ufind.htm


The `find -empty` command option allows the user to search for empty files or directories. An empty file would be a file that has no data and an empty directory would be one without any subdirectories or files.

Here, the `find written_2/ -empty` command goes through the `written_2/` directory to check if there are any empty files, which, in this case, is the `grep.txt` file as it contains no data. This command is helpful in finding empty files within directories and allowing for the user to carefully delete unwanted/empty files without deleting important files that already contain data.
```
find written_2/ -empty

written_2//grep.txt
```

In this example, we changed into one of the directories of `written_2/` to see if it had any files that are empty. As you can see, the `find non-fiction/ -empty` command goes through the `non-fiction` directory and finds its subdirectory, `Abernathy`, that contains an empty file called `ch0.txt`. The `-empty` command option is useful when searching through directories and subdirectories as users can find files that need to be modified or be deleted if necessary.  
```
find non-fiction/ -empty

non-fiction//OUP/Abernathy/ch0.txt
```

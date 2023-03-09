# Lab Report 5 - Researching a different Command: 'grep'
# 'grep'
The `grep` command is a command line utility that is used to search text and strings in a given file. In this report, we will be going over four `grep` command-line options that are used when searching given files or lines

## grep -H 
Sources:
* ChatGPT-Searched `What are some grep command-line options and what does each one do?
* GeeksforGeeks: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

Using the `grep -H` command-line option allows the user to look for a specific word and returns all files in which the word is found in. It outputs all the names of the files and each of their outputs. This can be a useful command-line option if the user is trying to search for a specific word and find the file, the name, and its contents where the word is located in.

In example 1, `grep -H` searches for the word "Berk" and finds the word in the results.txt file, displaying all instances of where the word is located. This helps the user view all possible files in which the word "Berk" is in.

## Example 1:
```
grep -H Berk results.txt

results.txt:written_2/non-fiction/OUP/Berk
results.txt:written_2/non-fiction/OUP/Berk/ch1.txt
results.txt:written_2/non-fiction/OUP/Berk/ch2.txt
results.txt:written_2/non-fiction/OUP/Berk/CH4.txt
results.txt:written_2/non-fiction/OUP/Berk/ch7.txt
```
In this example, `grep -H` searches for the word "Abernathy", and finds the word in the results.txt file, displaying all instances of where the word comes up. Like the previous example, this helps the user view all possible files where the word "Abernathy" is present. 

## Example 2: 
```
grep -H Abernathy results.txt

results.txt:written_2/non-fiction/OUP/Abernathy
results.txt:written_2/non-fiction/OUP/Abernathy/ch1.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch14.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch15.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch2.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch3.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch6.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch7.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch8.txt
results.txt:written_2/non-fiction/OUP/Abernathy/ch9.txt
```

## grep -i
Sources:
* ChatGPT-Searched `What are some grep command-line options and what does each one do?
* GeeksforGeeks: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

The `grep -i` command-line option performs a search for a specific word with case insensitivity. It outputs all the names of the files in which the word is present in, regardless if its upper or lower case. This can be a useful command-line option as it makes it easier for the user to find files with a specific word, without having to worry about case sensitivity.

Here, `grep -i` searches for the word "abernathy", with a lower case "a" and finds the word in the results.txt file, displaying all the path directories that includes the word "abernathy" despite having a lower case "a". This helps the user view all possible files that have the instances of "abernathy" without having to actually input the uppercase lettering. 

## Example 1:
```
grep -i abernathy results.txt

written_2/non-fiction/OUP/Abernathy
written_2/non-fiction/OUP/Abernathy/ch1.txt
written_2/non-fiction/OUP/Abernathy/ch14.txt
written_2/non-fiction/OUP/Abernathy/ch15.txt
written_2/non-fiction/OUP/Abernathy/ch2.txt
written_2/non-fiction/OUP/Abernathy/ch3.txt
written_2/non-fiction/OUP/Abernathy/ch6.txt
written_2/non-fiction/OUP/Abernathy/ch7.txt
written_2/non-fiction/OUP/Abernathy/ch8.txt
written_2/non-fiction/OUP/Abernathy/ch9.txt
``` 

In example 2, `grep -H` searches for the word "abernathy", but without using the `-i` command-line option, the search is case sensitive, preventing the user from finding the files with "Abernathy". 

## Example 2: 
```
grep -H abernathy results.txt
```
## grep --color
Sources:
* ChatGPT-Searched `What are some grep command-line options and what does each one do?
* GeeksforGeeks: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

The `grep --color` command-line option performs a search of a given word and highlights the word with a color to show the each instances of the word that exists. This can be a helpful command-line option for the user to have an easier view of the files with the word they searched.

As you can see below, `grep --color` highlights all instances of "Abernathy" of the path and text files. This is useful for the user to view the key term they are search for from results.txt

## Example 1:
```
grep --color Abernathy results.txt
```
![Screen Shot 2023-03-08 at 5 50 26 PM](https://user-images.githubusercontent.com/122497165/223894820-acfcb7de-2b02-4fb3-8473-217750b4fde6.png)

Just like the previous example, `grep --color Berk` highlights all instances of "Berk", showing the path and text files. This allows for the user to have a simple view of what files and paths they are working with under a certain key term.
## Example 2: 
```
grep --color Berk results.txt
```
![Screen Shot 2023-03-08 at 5 54 35 PM](https://user-images.githubusercontent.com/122497165/223895409-d19cda9d-7356-4468-bcfc-b6fccb2d43e7.png)

## grep -c
Sources:
* ChatGPT-Searched `What are some grep command-line options and what does each one do?
* GeeksforGeeks: [https://www.geeksforgeeks.org/grep-command-in-unixlinux/](https://www.geeksforgeeks.org/grep-command-in-unixlinux/)

Lastly, the `grep -c` command-line option gives the user the number of times a word exists within the file they're searching. This can be useful for the user to see how many times a specific word is present within their files.

Below, you can see that `grep -c Abernathy` finds 10 times where the word "Abernathy" appears within the file. This can help in finding the number of instances a key word appears in a file

## Example 1:
```
grep -c Abernathy results.txt

10
```
The same goes for this example. Like the previous, `grep -c Berk` finds 5 instances of the word "Berk" within the file. Using this command-line option can help the user count the number of instances a word appears in a file without having to go in and count each, individual file. 

## Example 2: 
```
grep -c Berk results.txt

5
```

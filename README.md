# Terminal Commands Reference Doc

### A quick reference guide for common terminal commands

#### Source: [The 50 Most Popular Linux & Terminal Commands - by Colt Steele](https://www.youtube.com/watch?v=ZtqBQ68cfJc&t=1s)

---

</br>

## NOTE

#### In the code examples I am using the following bracket syntax to indicate input from the user

```
$ mkdir [dirName1]
```

```
$ touch [fileName1]
```

#### [dirName1] or [fileName1] is a placeholder for the user's desired directory/file name. The actual command should look something like:

```
$ mkdir documents
```

```
$ touch favoriteFoods.txt
```

</br>

---

## Table of Contents

---

### Flags (yet to be added)

- [v](#v)
- [a](#a)
- [l](#l)
- [i](#i)
- [r](#r)
- [p](#r)
- enter more?

### Short Cuts

- [clear](#clear)
- [quit out](#quit-out)

### Current Location Info

- [pwd](#pwd)
- [ls](#ls)

### Navication

- [cd](#cd)
- [history](#history)

### File/Folder Creation

- [mkdir](#mkdir)
- [touch](#touch)

### File/Folder Deletion

- [rmdir](#rmdir)
- [rm](#rm)

---

### NOTE: from here down = yet to be formated

---

### File/Folder Manipulation

- [open directory](#open)
- [mv](#mv)
- [cp](#cp)

### File Content

- [>](#single-redirect)
- [>>](#double-redirect)
- [head](#head)
- [tail](#tail)
- [cat](#cat)
- [less](#less)
- [echo](#echo)
- [sort](#sort)
- [uniq](#uniq)
- [diff](#diff)
- [find](#find)
- [exec](#exec)
- [grep](#grep)

### Piping

- [piping](#piping)

### Expansions

- [~](#tilde)
- [Path Name Expansions](#path-name-expansions)

[Back To The Top](#terminal-commands-reference-doc)

</br>

---

# Commands

---

</br>

## Short Cuts

### Clear

To clear the contents of the terminal

```
$ clear
```

ctrl + l = clear shortcut

### Quit Out

Depending on what view you are in:

ctrl + c = quit out</br>
OR

```
$ q
```

---

# !!!Change 'back to the top' to be 'back to table of contents'

---

</br>

[Back To The Top](#terminal-commands-reference-doc)

---

## Current Location Info

### pwd

To print out the path of current directory

```
$ pwd
```

### ls

To print out the contents of the current directory

```
$ ls
```

Print contents of current directory in long form

```
$ ls -l
```

Print ALL files in current directory (includes hidden files)

```
$ ls -a
```

[Back To The Top](#terminal-commands-reference-doc)

---

## Navigation

### cd

To change directory

```
$ cd [dirName]
```

To back out one level

```
$ cd ..
```

To got to the home directory

```
$ cd ~
```

### history

Prints of list of all previous commands

```
$ history
```

To re-run a command from the history list

```
$ ![lineNumber]
```

To search the command history for any command that includes searchTerm (must be a string)

```
$ history | grep 'searchTerm'
```

[Back To The Top](#terminal-commands-reference-doc)

---

## File/Folder Creation

### mkdir

To create directories in current directory with name [dirName1] & [dirName2]

```
$ mkdir [dirName1] [dirName2]
```

To create a directory named [dirName2] inside of directory [dirName1]

```
$ mkdir [dirName1]/[dirName2]
```

To create any necessary folders to make the given folder structure a reality

```
$ mkdir -p [dirName1]/[dirName2]/[dirName3]
```

### touch

To create a file in the current directory named [name1]

```
$ touch [fileName1]
```

[Back To The Top](#terminal-commands-reference-doc)

---

## File/Folder Deletion

### rmdir

To delete folders [dirName1] & [dirName2] (only works on empty folders)

```
$ rmdir [dirName1] [dirName2]
```

### rm

To delete files or folders (CANNOT BE UNDONE!)

```
$ rm [fileName] [dirName]
```

To delete a directory and all of its contents

```
$ rm -r [dirName]
```

To choose what to delete and what to keep

```
$ rm -ri [dirName]
```

To get feedback about deletion files

```
$ rm -v [fileName] [dirName]
```

[Back To The Top](#terminal-commands-reference-doc)

---

## File/Folder Manipulation

### To open current dir in a new window
##### On Mac
```
$ open .
```

##### On Windows
```
$ start .
```

##### On Linux
```
$ xdg-open .
```
### mv
To move / rename files
```
$ mv [fileName1] [newName]
```
to move fileName1 into dirName
```
$ mv [fileName1] [dirName]
```

### cp
 To create copy with newName in current dir
```
$ cp [fileName1] [newName]
```
To create copy of file/directory in named directory with newName
```
$ cp [fileName(OR)dirName] [dirName]/[newName]
```

[Back To The Top](#terminal-commands-reference-doc)

---

## File Content

### Redirect
To redirect standard output AND REPLACE
```
$ [something] > [something]
```
To redirect standard output AND APPEND
```
$ [something] >> [something]
```
To replace content of fileName with the info coming from date. (If file does not exist fileName will be created and date data will be redirect into it).
```
$ date > [fileName]
```
To append the content of fileName with the info coming from date
```
$ date >> [fileName]
```
## head
Will print out the first 10 lines of the file
```
$ head [fileName]
```
Will print out the first 50 lines
```
$ head [file] -n50
```

tail = prints out the last 10 lines of the file

tail [file] = last 10 lines

tail [file] -n50 = last 50 lines

tail -f [file] = watches and will print any edits to that file

cat [file1] = print out the entire file

cat [file1] [file2] ... = print out all the content of all files

cat [file1] [file2] ... > [newFile] = combines the contents into a new file

cat -n [file1] = prints the contents with line numbers

less [file1] = shows the content of a file, but in a better format

once in the less format: space scrolls down one page at a time, 'b' scrolls up one page at a time, g takes you to the beginning of the file, shift + g takes you to the end of the file, a '/' followed by a word will search for that word.

echo "string" = prints "string" in terminal

echo "string" > [file1] = creates a file with contents of "string"

sort [file1] = will sort and print the contents of the file. does not mutate the original file. alphabetical by default. case sensitive. uppercase will be put before lowercase.

sort [file1] > [newFile] = contents of file1 are sorted and inserted into the new file.

sort -n [file1] = sort numerically

sort -r [file1] = reverse the order

sort -nr [file1] = reverse numeric sort

-u = only return unique items

sort -nu [file1] = numeric sort and only include unique numbers

cat [file1] [file2] | sort = pipe contents of two files to be sorted

sort -un nums | wc -l = returns the number of lines (items) in the file

uniq [file1] = prints content to terminal but omits ADJACENT duplicate values

sort [file1] | uniq = sorts contents then gives us the unique values.

sort [file1] | uniq -d = return only duplicate values

sort [file1] | uniq -u = return only non-duplicate lines

sort [file1] | uniq -c = return a count of how often each line repeats

sort [file1] | uniq -c | sort -n = returns a numericly sorted list of how many time seach line repeats

diff [file1] [file2] = [number1][letter][number2]
line number from file1, action character, line number from file1

diff -y [file1] [file2] = will show the differences of the two files side by side

diff -u [file1] [file2] = returns the diff format that git uses

find SEARCHES RECURSIVELY

find [location] [search params]
find . -name '*.js'
find documents -name '*7*'
find . -type d -name '*E*' (case sensitive)
find . -type d -iname '*E\*' (case insensitive)

-type d = only search directories
-type f = only search files

-or

find . -name 'E*' -or -name 'F*'

-exec

find . -type f -exec cat {} \;

{} is filled with the file name at execution time

grep = helps us find text inside of files.

grep [search term] -n [file1] = returns all lines that include the search term along with thier line numbers (thanks to -n)

ex. grep green -n songofmyself.txt = returns all lines that include the word green along with thier line number

grep -nC [number] [search term] [file1] = gives n lines of context before and after each line containing the search term

grep -r "term" . = searches for the term recursively through all files/folders which are nested from starting point "."

grep -r is case sensitive
grep -ri is case insensitive

grep works with regular expressions

maybe look for more teaching on grep

[Back To The Top](#terminal-commands-reference-doc)

---

## Piping

PIPING - (send output of one command and pass it to another command)

uses the pipe '|' character

ls -l | wc = [lines] [words] [bytes]

[Back To The Top](#terminal-commands-reference-doc)

---

## Expansions

Special syntax that is interpreted by the shell to mean something else

### Tilde

home directory

```
$ ~
```

### Path Name Expansions

- = matches all thing / all
  echo _ = returns every pathname in the current dir
  echo _.txt = returns anything that ends in .txt
  ls -l \*.txt = prints long list info about all .txt files

? = matches any single character
echo \*.??? = returns a list of all files that end with a dot '.' followed by any three characters. .txt .zip etc

{} = holds a list

takes the input and generates all possible combinations of what's in the list with what's outside of the list

echo {a,b,c}.txt = a.txt b.txt c.txt

touch app.{js,html,css,py} = will create 4 files:
app.js app.html app.css app.py

ls app.\* will list all files starting with 'app' that end in '.anything'

echo {1..99} = will return every number from 1 to 99 (inclusive)

echo Day{1..369} = returns Day1 Day2 Day3 ... Day 365

[Back To The Top](#terminal-commands-reference-doc)

---

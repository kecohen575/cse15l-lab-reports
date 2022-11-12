# Lab Report 3 - Researching the 'find' Command

> ## Option 1: '-name'

'-name' is an extremely useful command line option for 'find' as it allows us to search for patterns as opposed to just one specific name. For example, we can use it to find all the text files in a directory like this:
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/911report -name "*.txt"
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```
We can narrow our search even further to look for just files from Chapter 13.
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/911report -name "chapter-13*"
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
```
Although '-iname' is technically considered a separate option, I feel like it is useful to note since it seems like an extension of the use of '-name'. '-iname' does the same thing as '-name' but with case insensitivity, so you could change your search to this and still get the same result.
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/911report -iname "cHaPTeR-13*.txt"
./technical/911report/chapter-13.4.txt
./technical/911report/chapter-13.5.txt
./technical/911report/chapter-13.1.txt
./technical/911report/chapter-13.2.txt
./technical/911report/chapter-13.3.txt
```

> ## Option 2: '-delete'

The 'delete' option is exactly what it seems--it deletes the specified files and directories. Using this option returns no output if successful and returns an error if not. Calling this deleted the Media directory and all the files inside it.
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/government/Media -delete
```
This is what would happen if you called the same thing again. You get an error since the directory has already been deleted and no longer exists.
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/government/Media -delete
find: ./technical/government/Media: No such file or directory
```
We can also combine what we've learned about the name option to delete specific groups of files or directories. For example, if we wanted to now delete all the files from Chapter 13 in the 911report directory, we could call:
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/911report -name "chapter-13*" -delete
```

> ## Option 3: '-type'

The '-type' option specifies what type of item we are looking for. For the purposes of a CS15l student, only the file (f) and directory (d) types are relavant to use, but in the future I imagine we will become familiar with other types as well. We could use this to find all the directories in ./technical.
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical -type d
./technical
./technical/government
./technical/government/About_LSC
./technical/government/Env_Prot_Agen
./technical/government/Alcohol_Problems
./technical/government/Gen_Account_Office
./technical/government/Post_Rate_Comm
./technical/plos
./technical/biomed
./technical/911report
```
We could also use this option to find all the regular files in the 911report directory. (Note how the Chapter 13 files are now gone since we deleted them earlier)
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical/911report -type f
./technical/911report/chapter-3.txt
./technical/911report/chapter-2.txt
./technical/911report/chapter-1.txt
./technical/911report/chapter-5.txt
./technical/911report/chapter-6.txt
./technical/911report/chapter-7.txt
./technical/911report/chapter-9.txt
./technical/911report/chapter-8.txt
./technical/911report/preface.txt
./technical/911report/chapter-12.txt
./technical/911report/chapter-10.txt
./technical/911report/chapter-11.txt
```
Lastly, we could combine this with the '-name' option as well if we are worried about files and directories having the same name.
```
kevincohen@Kevins-MBP skill-demo1 % find ./technical -type d -name 911report
./technical/911report
```




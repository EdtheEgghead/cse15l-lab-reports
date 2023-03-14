# Lab Report \#5
  For this lab I will be looking at the `mv` command in Bash.

## `mv` command-line options

* `-f` 

  This command-line option makes it such that `mv` does not prompt for confirmation before overwriting the destination path. 
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  grep-temp.txt	temp-find.txt	temp-grep.txt	temp.txt	written_2
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % echo "$(cat temp.txt)"
  written_2/
  written_2//non-fiction
  written_2//non-fiction/OUP
  written_2//non-fiction/OUP/Berk
  written_2//non-fiction/OUP/Berk/ch2.txt
  written_2//non-fiction/OUP/Berk/ch1.txt
  written_2//non-fiction/OUP/Berk/CH4.txt
  written_2//non-fiction/OUP/Berk/ch7.txt
  written_2//non-fiction/OUP/Abernathy
  ...
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % touch temp1.txt
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -f temp1.txt temp.txt 
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  grep-temp.txt	temp-find.txt	temp-grep.txt	temp.txt	written_2
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % echo "$(cat temp.txt)"  

  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % 
  ```
  Here the a new and empty file is created is then is used to overwrite the original `temp.txt`, with the `-f` option, no warning messeges are printed and the process is just executed and eliminates the contents of the old file.
  
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % touch file.txt
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  file.txt	grep-temp.txt	temp.txt	written_2
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -i file.txt temp.txt 
  overwrite temp.txt? (y/n [n]) y
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  grep-temp.txt	temp.txt	written_2
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % touch file.txt         
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -i -f file.txt temp.txt
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  grep-temp.txt	temp.txt	written_2 
  ```
  Another use of `-f` is to override other `mv` options such as `-i` and `-n` to force your `mv` operation to be executed as seen above in which the first time it asks for confirmation but `-f` overrides that action.
***

* `-v`

  This command-line option means verbose and shows where the file is moved to after it is moved
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -v temp.txt ~/Documents/ucsd/cse15l
  temp.txt -> /Users/edgarseecof/Documents/ucsd/cse15l/temp.txt
  ```
  Here you can see `-v` being used to show you where the file was moved to
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -v ~/Documents/ucsd/cse15l/temp.txt .
  /Users/edgarseecof/Documents/ucsd/cse15l/temp.txt -> ./temp.txt
  ```
  Similarly, `-v` can be used when moving a file from a different directory into your current directory
***

* `-n`

  This command-line option forces `mv` to not overwrite an existing file
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  grep-temp.txt	temp.txt	written_2
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % echo "$(cat grep-temp.txt)"                                                             
  written_2//non-fiction/OUP/Berk/ch2.txt
  written_2//non-fiction/OUP/Berk/ch1.txt
  written_2//non-fiction/OUP/Berk/CH4.txt
  written_2//non-fiction/OUP/Berk/ch7.txt
  written_2//non-fiction/OUP/Abernathy/ch2.txt
  written_2//non-fiction/OUP/Abernathy/ch3.txt
  ...
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % echo "$(cat temp.txt)" 

  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -n grep-temp.txt temp.txt
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % echo "$(cat temp.txt)"      

  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % 
  ```
  The option `-n` option is especially useful if you are testing code and throwing around standard file names that may have useful output in them, thus preventing you from making a mistake. As seen here, the `-n` option doesn't change the contents of an existing file.
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % man mv
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -n grep-temp.txt file.txt
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % echo "$(cat file.txt)"      
  written_2//non-fiction/OUP/Berk/ch2.txt
  written_2//non-fiction/OUP/Berk/ch1.txt
  written_2//non-fiction/OUP/Berk/CH4.txt
  written_2//non-fiction/OUP/Berk/ch7.txt
  written_2//non-fiction/OUP/Abernathy/ch2.txt
  written_2//non-fiction/OUP/Abernathy/ch3.txt
  written_2//non-fiction/OUP/Abernathy/ch1.txt
  written_2//non-fiction/OUP/Abernathy/ch7.txt
  written_2//non-fiction/OUP/Abernathy/ch6.txt
  ...
  ```
  Likewise, `-n` can be useful because it safeguards against overwriting useful data but still permits the copying of text from one file to another if the given comman would not have overwritten information.
***

* `-i`

  This command-line option makes it so that the command line asks for permission to overwrite a file.
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % touch file.txt
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -i file.txt temp.txt 
  overwrite temp.txt? (y/n [n]) y
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  temp.txt	written_2
  ```
  In this example you can see the use of `-i` becasue it tells you if you are about to make a mistake and asks for further confirmation to perform a risky action.
  
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  file.txt	temp.txt	written_2
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % mv -i -n file.txt temp.txt 
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % ls
  file.txt	temp.txt	written_2
  ```
  Another niche behavior of `-i` is that `-n` negates its effects, meaning that it does not ask for confirmation or even have the ability to overwrite files in its presence.
***

## Sources used:
1. Built in manuals- For generic describtion of different options that are available.
2. ChatGPt- For help developing examples and command debugging.
3. https://en.wikibooks.org/wiki/Grep - Used to double check other two sources.

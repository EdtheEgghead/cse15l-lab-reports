# Lab Report \#3
  For this lab I will be looking at the `grep` command in Bash.

## `grep` command-line options

* `-i` 

  This command-line option, or the equivalent `--ignore-case` option ignores case. For example, `example` is treated the same as `Example` when grepping.
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % grep -c 'people' Athens-Intro.txt
  3
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % grep -c -i 'people' Athens-Intro.txt
  5
  ```
  Suppose you wanted to find count how many times the string `people` was used in `Athens-Intro.txt`     with `-c` the useful option `-i` gives you an accurate   count as it ignores case as seen between       command one and command two above.
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -r -l athens
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -r -l -i athens
  ./written_2/non-fiction/OUP/Rybczynski/ch3.txt
  ./written_2/travel_guides/berlitz1/HistoryItaly.txt
  ./written_2/travel_guides/berlitz1/WhereToGreek.txt
  ./written_2/travel_guides/berlitz1/HistoryIstanbul.txt
  ./written_2/travel_guides/berlitz1/WhereToItaly.txt
  ./written_2/travel_guides/berlitz1/HistoryGreek.txt
  ./written_2/travel_guides/berlitz1/WhereToEdinburgh.txt
  ./written_2/travel_guides/berlitz1/WhereToIsrael.txt
  ./written_2/travel_guides/berlitz1/IntroGreek.txt
  ./written_2/travel_guides/berlitz1/WhatToGreek.txt
  ./written_2/travel_guides/berlitz1/HistoryEdinburgh.txt
  ./written_2/travel_guides/berlitz2/Berlin-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Barcelona-History.txt
  ./written_2/travel_guides/berlitz2/Boston-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Berlin-History.txt
  ./written_2/travel_guides/berlitz2/Crete-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Athens-History.txt
  ./written_2/travel_guides/berlitz2/Canada-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Athens-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Athens-Intro.txt
  ./written_2/travel_guides/berlitz2/Athens-WhatToDo.txt
  ```
  Another use of `-i` is in finding where the name of a proper noun appears. Although in this case it     does not apply because all instances of `Athens` are uppercase, it would be useful in the case that     the writer of the text file did not capitalize properly
***

* `-c`

  This command-line option, or the equivalent `--count` option, counts the number of times the given string appears in a file.
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % grep -c 'people' Athens-Intro.txt
  3
  ```
  Here you can see `-c` being used to count the number of times the string `people` appears in a file.
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % pwd  
  /Users/edgarseecof/repos/skill-demo1-data/written_2/travel_guides/berlitz2
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % grep -r -c people ./Bahamas*.txt
  ./Bahamas-History.txt:2
  ./Bahamas-Intro.txt:1
  ./Bahamas-WhatToDo.txt:1
  ./Bahamas-WhereToGo.txt:16
  ```
  Using `-c` in conjunction with `-r` allows the ability to find the count of a string in numerous       files, for example here we recursively search through every file with Bahamas*.txt and count the       number of the string `people` in each one.
***

* `-r`

  This command-line option is also equivalent to `-R` or `--recursive` and allows you to recursively search through a directory for a desired sub-string.
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -rl Puerto
  ./written_2/non-fiction/OUP/Castro/chR.txt
  ./written_2/travel_guides/berlitz1/HistoryJamaica.txt
  ./written_2/travel_guides/berlitz1/WhatToFWI.txt
  ./written_2/travel_guides/berlitz1/HistoryHawaii.txt
  ./written_2/travel_guides/berlitz1/WhereToMallorca.txt
  ./written_2/travel_guides/berlitz2/Costa-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Cuba-WhatToDo.txt
  ./written_2/travel_guides/berlitz2/Cancun-WhatToDo.txt
  ./written_2/travel_guides/berlitz2/Vallarta-History.txt
  ./written_2/travel_guides/berlitz2/Cancun-History.txt
  ./written_2/travel_guides/berlitz2/PuertoRico-WhatToDo.txt
  ./written_2/travel_guides/berlitz2/Vallarta-WhatToDo.txt
  ./written_2/travel_guides/berlitz2/CstaBlanca-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/PuertoRico-History.txt
  ./written_2/travel_guides/berlitz2/PuertoRico-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Cuba-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Costa-WhatToDo.txt
  ./written_2/travel_guides/berlitz2/CanaryIslands-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/CanaryIslands-WhatToDo.txt
  ./written_2/travel_guides/berlitz2/Vallarta-WhereToGo.txt
  ./written_2/travel_guides/berlitz2/Cancun-WhereToGo.txt
  ```
  The option `-r` is especially useful because it allows you to search through all directories and       subdirectories present, as opposed to individual files.
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % ls                                 
  Algarve-History.txt		Berlin-WhatToDo.txt		CostaBlanca-History.txt
  ...                   ...                   ...
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % grep -rl Bahamas                   
  ./Bahamas-WhereToGo.txt
  ./Canada-WhereToGo.txt
  ./Bahamas-Intro.txt
  ./Bahamas-WhatToDo.txt
  ./Bahamas-History.txt
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro berlitz2 % grep -l Bahamas Algarve-History.txt
  ```
  This example shows how much faster using the `-r` option is as opposed to checking each individual     file in the directory for `Bahamas`, the `-r` option allows the process to be automated and outputs
  the desired files.
***

* `-l`

  This command-line option makes it so that grep outputs the file path of files that have the desired sub-string.
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -r -l Lucayans
  ./written_2/travel_guides/berlitz2/Bahamas-History.txt
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -r Lucayans   
  ./written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a ...    
  ./written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in ...  
  ```
  In this example you can see the use of `-l` becasue it shows you where the substring you are looking   for is with a path and does not fill up your terminal with the text containing the substring. Also     it shows how `-l` makes grep only search a file until one match has been found.
  
  ## Example 2
  ```
  edgarseecof@Edgars-MacBook-Pro written_2 % grep -rl '' > temp-grep.txt
  edgarseecof@Edgars-MacBook-Pro written_2 % wc -l temp-grep.txt         
     226 temp-grep.txt
  ```
  Another niche use case of '-l' is to find the number of files and directories that are present in a directory by using grep with `''` as its argument as   seen in the above snipppet. Note that this number includes the directories in the `written_2` directory not only `*.txt` files.
***

## Sources used:
1. Built in manuals- For generic describtion of different options that are available.
2. ChatGPt- For help developing examples and command debugging.
3. https://en.wikibooks.org/wiki/Grep - Used to double check above two sources.

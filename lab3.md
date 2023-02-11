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
  Suppose you wanted to find count how many times the string `people` was used in `Athens-Intro.txt` with `-c` the useful option `-i` gives you an accurate   count as it ignores case as seen between command one and command two above.
  ## Example 2
  ```
  *INSERT CODE HERE*
  ```
---
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
  Using `-c` in conjunction with `-r` allows the ability to find the count of a string in numerous files, for example here we recursively search through     every file with Bahamas*.txt and count the number of the string `people` in each one.
---
* `-r`

  This command-line option is also equivalent to `-R` or `--recursive` and allows you to recursively search through a directory for a desired sub-string.
  ## Example 1
  ```
  *INSERT CODE HERE*
  ```
  ## Example 2
  ```
  *INSERT CODE HERE*
  ```
---
* `-l`

  This command-line option makes it so that grep outputs the file path of files that have the desired sub-string.
  ## Example 1
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -r -l Lucayans
  ./written_2/travel_guides/berlitz2/Bahamas-History.txt
  ```
  ```
  edgarseecof@Edgars-MacBook-Pro skill-demo1-data % grep -r Lucayans   
  ./written_2/travel_guides/berlitz2/Bahamas-History.txt:Centuries before the arrival of Columbus, a peaceful Amerindian people who called themselves the     Luccucairi had settled in the Bahamas. Originally from South America, they had traveled up through the Caribbean islands, surviving by cultivating modest   crops and from what they caught from sea and shore. Nothing in the experience of these gentle people could have prepared them for the arrival of the       Pinta, the Niña, and the Santa Maria at San Salvador on 12 October 1492. Columbus believed that he had reached the East Indies and mistakenly called       these people Indians. We know them today as the Lucayans. Columbus claimed the island and others in the Bahamas for his royal Spanish patrons, but not     finding the gold and other riches he was seeking, he stayed for only two weeks before sailing towards Cuba.
  ./written_2/travel_guides/berlitz2/Bahamas-History.txt:The Spaniards never bothered to settle in the Bahamas, but the number of shipwrecks attest that     their galleons frequently passed through the archipelago en route to and from the Caribbean, Florida, Bermuda, and their home ports. On Eleuthera the       explorers dug a fresh-water well — at a spot now known as “Spanish Wells” — which was used to replenish the supplies of water on their ships before they   began the long journey back to Europe with their cargoes of South American gold. As for the Lucayans, within 25 years all of them, perhaps some 30,000     people, were removed from the Bahamas to work — and die — in Spanish gold mines and on farms and pearl fisheries on Hispaniola (Haiti), Cuba, and           elsewhere in the Caribbean.
  ```
  
  In this example you can see the use of `-l` becasue it shows you where the substring you are looking for is with a path and does not fill up your           terminal with the text containing the substring. Also it shows how `-l` makes grep only search a file until one match has been found.
  
  ## Example 2
  ```
  *INSERT CODE HERE*
  ```
---
## Sources used:
1. https://en.wikibooks.org/wiki/Grep
2. ChatGPt
3. Built in manuals

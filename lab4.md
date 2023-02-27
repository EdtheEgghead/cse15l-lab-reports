# Lab Report #4

## Steps 4 to 9

4) Log into ieng6
  - Hit `<control>` + `<r>` at the same time
  - Then type `ssh`, and hit `<enter>`, the first results should be your most recent use of `ssh cs15lwi23awh@ieng6.ucsd.edu` or if it was not found I could type it out
  - Hit `<enter>` and you should be at a screen like the one below
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-02-26%20at%209.59.34%20PM.png)
---

5) Clone your fork of the repository from your Github account
  - First go to the lab7 github page and copy the ssh repository code
  - Then type `git clone <repo-ssh>` where `<repo-ssh>` is the ssh key that you just copied
  - Hit `<enter>`
  - If you also type `ls` then hit `<enter>` you should get a screen like the one below
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-02-26%20at%2010.04.56%20PM.png)
---

6) Run the tests, demonstrating that they fail
  - Change directories into the repository you just clone by typing `cd l` then hitting `<tab>` and then hitting `<enter>`
  - Then hit `<control>` + `<r>` at the same time
  - Then type `javac `, and hit `<enter>`, the first results should be your most recent use of `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` or if it was not found I could type it out
  - Then hit `<control>` + `<r>` at the same time
  - Then type `java -`, and hit `<enter>`, the first results should be your most recent use of `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` or if it was not found I could type it out. Make sure to double check that the name of the class is `ListExamplesTests`
  - After this you should get a screen like the one below
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-02-26%20at%2010.13.01%20PM.png)
---

7) Edit the code file to fix the failing test
  - Next type `nano L`, then without hitting `<enter>`, hit `<tab>`, then type `.j' and hit `<tab>` then hit `<enter>`
  - Then hit `<control>` + `<w>` at the same time and type `index1 += 1;` then hit `<enter>`
  - Then hit `<control>` + `<w>` then hit `<enter>`
  - Then hit `<control>` + `<w>` then hit `<enter>`
  - Then hit `<right-arrow>`
  - Then hit `<right-arrow>`
  - Then hit `<right-arrow>`
  - Then hit `<right-arrow>`
  - Then hit `<right-arrow>`
  - Then hit `<right-arrow>`
  - Then hit `<delete>` and type `2`, then hit `<control>` + `<o>` and hit `<enter>`
  - Then hit `<control>` + `<x>`
  - If you followed the steps you can type `less L` then without hitting `<enter>`, hit `<tab>`, then type `.j` and hit `<tab>` then hit `<enter>` and you should see a screen like the one below, you can exit this screen by hitting `<q>`, notice the changes you made are still there.
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-02-26%20at%2010.26.30%20PM.png)
---

8) Run the tests, demonstrating that they now succeed
  - Then hit `<control>` + `<r>` at the same time
  - Then type `javac `, and hit `<enter>`, the first results should be your most recent use of `javac -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar *.java` or if it was not found I could type it out
  - Then hit `<control>` + `<r>` at the same time
  - Then type `java -`, and hit `<enter>`, the first results should be your most recent use of `java -cp .:lib/hamcrest-core-1.3.jar:lib/junit-4.13.2.jar org.junit.runner.JUnitCore ListExamplesTests` or if it was not found I could type it out. Make sure to double check that the name of the class is `ListExamplesTests`
  - After this you should get a screen like the one below, with the tests passed.
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-02-26%20at%2010.37.15%20PM.png)
---

9) Commit and push the resulting change to your Github account
  - First type `git status` to see what changes you have made
  - Next type `git add --all` 
  - Next type `git status` again to see if the files were added to the staging area
  - Then type `git commit -m "Fixed one bug"` to commit your files with a message
  - Finally type `git push origin main` to push your files to github
  - Now you are done and all the outputs of the commands you just typed should look something like the image below
![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-02-26%20at%2010.50.54%20PM.png)

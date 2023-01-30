# Lab 1 Lab Report
## Installling Visual Studio Code
To install Visual Studio Code(VScode) you go to [https://code.visualstudio.com/](https://code.visualstudio.com/) and follow the provided instructions and eventually will find with a display that looks like the below screenshot.

![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-01-12%20at%204.09.43%20PM.png)

## Remotely Connecting
If you are on mac, you are able to remote connect to servers on your machine out of the box. To do this, you type open a terminal in VScode by hitting "Control + shift + \`" then typing: 
`ssh cs15lwi23zzz@ieng6.ucsd.edu` 
where zzz is replaced with the three letters corresponding to your account. After typing in the above command and typing `yes`, you enter your
password that accompanies your cse15l account to connect to the remote server. If you succesfully connect your terminal window
should look similar to the below screenshot.

![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-01-12%20at%204.38.31%20PM.png)

If you want to exit your remote server you can use "Control + D" on your keyboard or type `exit` into your active terminal.

## Trying Some Commands
After you connect to the remote server you can practice navigating about the file system present. The list below explains the commands used in the below screenshot.
1. `ls` - Typing `ls` into the command line aptly lists the contents in the directory that remote connection has left you in.
2. `mkdir` - Typing `mkdir <directory name` makes a new directory called said name. When you then type `ls` you see that you've created a new directory.
4. `touch` - Typing `touch <file name>` allows you to create a file with a specific name.
5. `mv` - Typing `mv <file name> <destination directory>` moves a file from the current directory to the destination directory. Thus `hello.txt` is moved from the current directory to the practice directory. Also note that the `.` before `/practice` signals the current directory your reside in.
6. `cd` - Finally by changing directories using the `cd <directory name>` into the practice directory and listing its contents using `ls` we see that `hello.txt` has been moved to a different directory.

![Image](https://edtheegghead.github.io/cse15l-lab-reports/Screenshot%202023-01-12%20at%205.47.25%20PM.png)

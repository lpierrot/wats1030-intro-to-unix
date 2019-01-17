# *nix Scavenger Hunt

Complete the following challenges using the command-line interface on your favorite
Unix or Linux operating system. You are welcome and encouraged to consult any
additional documentation online or in books.

Please add your answers/responses/text pastes to the document after each prompt.

Note: For some of the challenges you will need to reference files included with
this repository, so you will need to fork the repo into your own Github account
and then clone it to your development environment.

## The Challenges

### Navigating the Filesystem

* Get an idea of where you are in the operating system. Use the `pwd` command to find your "path to working directory"--your current location in the filesystem of your devbox. *Paste the output of the `pwd` command here:* 
...
/Users/kidistwinters/projects
...
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
...
lpierrot.github.io              wats3010-adv-markup             wats3010-intro-to-bootstrap-4   wats3020
wats1030-intro-to-unix          wats3010-css                    wats3010-product-page           zen-bootstrap
...
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
...
When using "ls-alh" I get a list of files. drwxr-xr-x  11 kidistwinters  staff   352B Jan 16 17:18 .
drwxr-xr-x+ 32 kidistwinters  staff   1.0K Jan 10 18:35 ..
-rw-r--r--@  1 kidistwinters  staff    10K Jan 16 15:57 .DS_Store
drwxr-xr-x   7 kidistwinters  staff   224B Jan  8 19:58 lpierrot.github.io
drwxr-xr-x   9 kidistwinters  staff   288B Jan 16 17:18 wats1030-intro-to-unix
drwxr-xr-x  13 kidistwinters  staff   416B Dec  6 18:37 wats3010-adv-markup
drwxr-xr-x   9 kidistwinters  staff   288B Dec  6 18:36 wats3010-css
drwx------@ 37 kidistwinters  staff   1.2K Dec  5 19:40 wats3010-intro-to-bootstrap-4
drwxr-xr-x  16 kidistwinters  staff   512B Dec 11 23:24 wats3010-product-page
drwxr-xr-x   4 kidistwinters  staff   128B Jan 15 18:36 wats3020
drwxr-xr-x  10 kidistwinters  staff   320B Dec  6 18:46 zen-bootstrap

But when I use the command "-alh" it returns a no file found
bash: -alh: command not found
...
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
...
kidists-MacBook-Pro:projects kidistwinters$ man
What manual page do you want?
kidists-MacBook-Pro:projects kidistwinters$ man a
No manual entry for a
kidists-MacBook-Pro:projects kidistwinters$ man l
No manual entry for l
kidists-MacBook-Pro:projects kidistwinters$ ma h
bash: ma: command not found
...
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
...
Applications                    System                          Volumes                         etc                             private                         var
Library                         User Information                bin                             home                            sbin                            vm
Network                         User Information (from old Mac) cores                           installer.failurerequests       tmp
OS X Install Data               Users                           dev                             net                             usr
...
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
...
DESCRIPTION
     Shell builtin commands are commands that can be executed within the running shell's process.  Note that, in the case of csh(1) builtin commands, the command is executed in a subshell if it occurs as any
     component of a pipeline except the last.

     If a command specified to the shell contains a slash ``/'', the shell will not execute a builtin command, even if the last component of the specified command matches the name of a builtin command.
     Thus, while specifying ``echo'' causes a builtin command to be executed under shells that support the echo builtin command, specifying ``/bin/echo'' or ``./echo'' does not.
...
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
...
idists-MBP:projects kidistwinters$ cd
kidists-MBP:~ kidistwinters$ ~
bash: /Users/kidistwinters: is a directory
kidists-MBP:~ kidistwinters$ pwd
/Users/kidistwinters
...
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
...
0
...
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
...
Applications                                            Family Resource Exchange Volunteer Info Packet.pdf      One Million Meals LITERACY CORPS.docx                   Sites
Desktop                                                 Google Drive                                            Pictures                                                projects
Documents                                               Library                                                 Public                                                  scan0010.jpg
Downloads                                               Movies                                                  README.md                                               ~$ Analyst Position .docx
Drug Screen.pdf                                         Music                                                   Resume and Cover letter
...
* Press the up arrow on your keyboard. *What just happened?*
...
It takes me up to the previous command inputs
...
* Press the up arrow a few more times. *What do you see?*
...
All the command inputs that entered previously
...
* Run the `history` command. *What do you see?*
...
All the commands that I have ever entered in the terminal
..
### Observing the System

* Discover what account you are logged into using the `whoami` command. *What username are you currently using?*
...
kidistwinters
...
* Discover who else is on your system with the `who` command. *Are any other users using your system? If so, list them here:*
...
kidistwinters console  Jan  8 18:08
kidistwinters ttys001  Jan 16 16:26
...
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
...
19:02  up 8 days, 56 mins, 2 users, load averages: 1.31 1.30 1.25
...
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
...
Shows all the users' processes, it is listed by username, it shows me all the information on my computer including CPU, etc
...
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
...
With this command I see all my processor activity. it is basically like task manager.
...
### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
...
I did not find any files. Everytime I run the command 'challenge_files' for some reason it keeps saying command not found. 
...
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
...
Command not found
...
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
...
For some reason I am not getting the correct commands for challenge_files. This what I got:
usage: find [-H | -L | -P] [-EXdsx] [-f path] path ... [expression]
       find [-H | -L | -P] [-EXdsx] -f path [path ...] [expression]
...
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
...

...
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
...

...
### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
...
-rw-r--r--   1 kidistwinters  staff   160B Jan 16 19:40 files.txt
...
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
...
it shows me all my files including files.txt
...
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
...
kidistwinters    10067   0.0  0.4  4332428  15980   ??  S     7:40PM   0:00.15 /System/Library/PrivateFrameworks/AOSKit.framework/Versions/A/XPCServices/com.apple.iCloudHelper.xpc/Contents/MacOS/com.apple.iCloudHelper
kidistwinters    10066   0.0  0.4  4352572  18448   ??  Ss    7:40PM   0:00.23 /System/Library/Frameworks/QuickLook.framework/Versions/A/Resources/quicklookd.app/Contents/XPCServices/QuickLookSatellite.xpc/Contents/MacOS/QuickLook
kidistwinters    10064   0.0  0.3  4850000  13208   ??  S     7:40PM   0:00.17 /System/Library/Frameworks/QuickLook.framework/Resources/quicklookd.app/Contents/MacOS/quicklookd
_spotlight       10044   0.0  0.3  4342000  10996   ??  S     7:38PM   0:00.10 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m
kidistwinters    10030   0.0  0.0  4277236    476 s002  S+    7:33PM   0:00.01 grep .user
kidistwinters     9908   0.0  1.6  4839716  65436   ??  S     7:26PM   0:05.75 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-tri
kidistwinters     9203   0.0  0.0  4296508    940 s002  Ss    6:47PM   0:00.12 /bin/bash -l
_spotlight        9099   0.0  0.2  4315440  10352   ??  S     6:41PM   0:00.12 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m
kidistwinters     9037   0.0  0.7  4336720  29072   ??  S     6:39PM   0:01.13 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m
...

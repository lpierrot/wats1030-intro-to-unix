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
/Users/kidistwinters/projects/wats1030-intro-to-unix
...
* Discover more about this filesystem. Use `ls` (the "list" command)to see what is in this directory. *What directories and files do you see when you run `ls`?* 
...
LICENSE                         challenge_files                 nix_scavenger_hunt_stretch.md
README.md                       nix_scavenger_hunt.md           super_scavengers.md
...
* You can use *options* to modify how a command runs. Try using `ls -alh` to see the contents of your current directory. *How are the results different when you use the `-alh` options?*
...
drwxr-xr-x    9 kidistwinters  staff   288B Jan 16 17:18 .
drwxr-xr-x   12 kidistwinters  staff   384B Jan 16 19:40 ..
drwxr-xr-x   14 kidistwinters  staff   448B Jan 16 20:23 .git
-rw-r--r--    1 kidistwinters  staff   1.1K Jan 16 17:18 LICENSE
-rw-r--r--    1 kidistwinters  staff   2.7K Jan 16 17:18 README.md
drwxr-xr-x  111 kidistwinters  staff   3.5K Jan 16 17:18 challenge_files
-rw-r--r--    1 kidistwinters  staff    12K Jan 17 08:59 nix_scavenger_hunt.md
-rw-r--r--    1 kidistwinters  staff   326B Jan 16 20:12 nix_scavenger_hunt_stretch.md
-rw-r--r--    1 kidistwinters  staff   255B Jan 16 17:18 super_scavengers.md
...
* The `man` ("manual") command tells you more about how any given command works. (*WARNING:* CodeAnywhere does not support the man command. You can click the following link to complete this task: http://man.he.net/). Run `man` to see instructions about how to use `man`. Then use `man` to learn what the `a`, `l`, and `h` options mean when used with the `ls` command. *Write down what those options do?*
...
a: Include directory entries whose names begin with a dot (.).
l: (The lowercase letter ``ell''.)  List in long format.  (See below.)  If the output is to a terminal, a total sum for all the    file sizes is output on a line before the long listing.
h: When used with the -l option, use unit suffixes: Byte, Kilobyte, Megabyte, Gigabyte, Terabyte and Petabyte in
   order to reduce the number of digits to three or less using base 2 for sizes.
...
* Commands can also take *arguments*, which are usually the names of files or locations that you want the command to work with. Try running `ls /` to see what files are in the *root* directory of the filesystem. *What files and directories do you see listed?*
...
Applications                    User Information (from old Mac) etc                             tmp
Library                         Users                           home                            usr
Network                         Volumes                         installer.failurerequests       var
OS X Install Data               bin                             net                             vm
System                          cores                           private
User Information                dev                             sbin
...
* A Unix filesystem has a few special shortcuts to refer to specific locations. `/` indicates the *root* of the filesystem, meaning the top-most directory in the filesystem hierarchy. Use the `cd` ("change directory") command to move to the root directory. (Hint: Use `man` to look up the `cd` command if you have any issues) *Then run `pwd` and paste the output here:*
...

/
...
* Another special shortcut in Unix is the `~` location. This indicates the *user root* directory, meaning the top-most directory in the hierarchy that comes below your user account. Use `cd` to move to `~`. *Run `pwd` and paste the response here:*
...
/Users/kidistwinters
...
* Change directory into the `challenge_files` directory. Use `ls` to find only the files with a `.demo` pattern. *How many files do you find?*
...
2015_special_stuff.demo         cloaked-wookie.demo             scooter-double-mamba.demo
...
* Use the `cd` command to move "up" one directory. *Where are you in the filesystem now?*
...
/Users/kidistwinters/projects/wats1030-intro-to-unix
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
...
* How long has your system been running? Use `uptime` to see, and *paste the result here:*
...
19:00  up 13 days, 54 mins, 1 user, load averages: 1.55 1.53 2.30
...
* Run `ps aux` and review the results. (Hint: Use `man` to learn more about the `ps` command and options.) *How do you interpret what you see here?*
...
Display information about other users' processes as well as your own.  This will skip any processes which do
not have a controlling terminal, unless the -x option is also specified.
...
* Run `top` and review the results. (Hint: You may need to use `ctrl-c` to get out of this app.) *How do you interpret what you see here?*
...
With this command I see all my processor activity. it is basically like task manager. It shows everything that's running on the computer. 
...
### Finding and Viewing Files

* Make sure you are in the `challenge_files` directory. Use the `*` wildcard to find all the files that have the word "credit" in the filename. *How many files did you find?*
...
kidists-MacBook-Pro:challenge_files kidistwinters$ ls *credit*
credit_cards.txt        credit_cards2.txt
...
* Use the `more` command to view one of the `credit_cards` files you just discovered. (Hint: Type `q` to quit viewing the file. Press the `spacebar` to page down. Use your keyboard arrows to move up/down.) *What is the date in the file you have viewed?*
...
01-15-2015
...
* Use the `find` command to search for files more effectively. Search the sub-directories under `challenge_files` to find the location of the file named `modi_laboriosam.txt`. *Where is that file located?*
...
./tmp/modi_laboriosam.txt
...
* Use the `grep` command to search for text within a file. Use `grep` on all the `.user` files in `challenge_files` to find which files contain "WA" (the abbreviation for Washington state). *How many files did you find?*
...
Britt-Erdman.user:O'Harachester, WA 37261
Lissie-Strosin.user:Jewessfurt, WA 00816-7241
...
* Use the `-r` option of `grep` to *recursively* find the text "Waldo" hidden in a file somewhere under the `challenge_files` directory. *Paste the result showing the file and line where the word "Waldo" shows up.*
...
serial-numbers/eaque_molestiae.txt:Ut est maiores quia autem. Nisi modi Waldo sed corporis sit explicabo ut est. Et est placeat ea sunt sunt consectetur sunt incidunt. Explicabo vel esse blanditiis dolorem culpa non quia.
...
### Pipes and Connecting Commands

* Sometimes it's useful to output the results of a command to a text file for further analysis, reference, or processing. Try running `ls > files.txt`. Notice that the file `files.txt` was created. View that file using `more`. *What do you see in the `files.txt` file?*
...
01
2015_special_stuff.demo
Afton-Jast.user
Aimee-Maggio.user
Alfonso-Gottlieb.user
Allen-Kemmer.user
Almina-Cormier.user
Alta-Lemke.user
Amina-McGlynn.user
Anabel-Hammes.user
Ancel-Conn.user
Anjali-Halvorson.user
Ardath-Kuvalis.user
Avah-Dickinson.user
Ayaan-Stiedemann.user
Aylin-Grant.user
Bedford-Sipes.user
Benita-King.user
Benito-Stoltenberg.user
Beverlee-Moen.user
Brad-Thiel.user
Brayan-Douglas.user
Bria-Satterfield.user
Bridgette-Reichel.user
Britt-Erdman.user
Britta-Hammes.user
Bryant-Kuhic.user
Bryton-Aufderhar.user
Caitlin-Grady.user
Carroll-Hartmann.user
Claudie-McClure.user
Clemente-Haley.user
Cleo-VonRueden.user
Codie-Romaguera.user
Cooper-Reynolds.user
Corrie-Bogisich.user
Dannielle-Green.user
Deedee-Jacobson.user
Desiree-Marks.user
Deven-Rutherford.user
Doyle-Jones.user
Dustyn-O'Connell.user
Elza-Mraz.user
Emory-Crona.user
Erin-Walker.user
01
2015_special_stuff.demo
Afton-Jast.user
Aimee-Maggio.user
Alfonso-Gottlieb.user
Allen-Kemmer.user
Almina-Cormier.user
Alta-Lemke.user
Amina-McGlynn.user
Anabel-Hammes.user
Ancel-Conn.user
Anjali-Halvorson.user
Ardath-Kuvalis.user
Avah-Dickinson.user
Ayaan-Stiedemann.user
Aylin-Grant.user
Bedford-Sipes.user
Benita-King.user
Benito-Stoltenberg.user
Beverlee-Moen.user
Brad-Thiel.user
Brayan-Douglas.user
Bria-Satterfield.user
Bridgette-Reichel.user
Britt-Erdman.user
Britta-Hammes.user
Bryant-Kuhic.user
Bryton-Aufderhar.user
Caitlin-Grady.user
Carroll-Hartmann.user
Claudie-McClure.user
Clemente-Haley.user
Cleo-VonRueden.user
Codie-Romaguera.user
Cooper-Reynolds.user
Corrie-Bogisich.user
Dannielle-Green.user
Deedee-Jacobson.user
Desiree-Marks.user
Deven-Rutherford.user
Doyle-Jones.user
Dustyn-O'Connell.user
Elza-Mraz.user
Emory-Crona.user
Erin-Walker.user
Estela-Schultz.user
Fernanda-Tromp.user
Fletcher-Rice.user
Fred-Ryan.user
Genie-Abshire.user
Grace-Tromp.user
Grant-Cronin.user
Hali-Roob.user
Harland-Schoen.user
Harrell-Quitzon.user
Hillard-Ziemann.user
Isadora-Leffler.user
Jaxen-Gleichner.user
Jayme-Rodriguez.user
Jenni-O'Connell.user
Johny-Borer.user
Kassandra-Barrows.user
Keely-Hilpert.user
Kenyatta-Hickle.user
Kiana-Kulas.user
Kirstin-Hoppe.user
Kwame-Schmitt.user
Ladonna-Lueilwitz.user
Lala-Will.user
Leia-Hudson.user
Leia-Ziemann.user
Lillard-Purdy.user
Lilly-Kohler.user
Lissie-Strosin.user
Mannie-Ritchie.user
Masako-Lind.user
Melisa-Yundt.user
Michelina-Kuphal.user
Minnie-Jacobi.user
Murdock-Leffler.user
Mychal-Corkery.user
Nakita-Nader.user
Nayely-Dare.user
Nicholas-Strosin.user
Niles-Runte.user
Nina-Sporer.user
Noreta-Steuber.user
Ovid-Bogan.user
Randell-Sauer.user
Remy-Renner.user
Ronna-Hermann.user
Rosalind-Wisozk.user
Rosena-Simonis.user
Sandie-Balistreri.user
Sharen-Hansen.user
Sherrill-Russel.user
Sherwin-Kovacek.user
Sherwood-Rath.user
Shyheim-Murazik.user
Siobhan-Kirlin.user
Tomas-Kutch.user
cloaked-wookie.demo
credit_cards.txt
credit_cards2.txt
files.txt
scooter-double-mamba.demo
serial-numbers
test2
tmp
wow
...
* Notice that if you run `ls -alh` in the `challenge_files` directory, the files scroll by very quickly. Sometimes it would be better to get the results in a paginated format. Try running `ls -alh | more`. *Describe what you see when you run `ls -alh | more`.*
...
total 864
drwxr-xr-x  112 kidistwinters  staff   3.5K Jan 21 19:30 .
drwxr-xr-x    9 kidistwinters  staff   288B Jan 16 17:18 ..
drwxr-xr-x   27 kidistwinters  staff   864B Jan 16 17:18 01
-rw-r--r--    1 kidistwinters  staff     0B Jan 16 17:18 2015_special_stuff.demo
-rw-r--r--    1 kidistwinters  staff    93B Jan 16 17:18 Afton-Jast.user
-rw-r--r--    1 kidistwinters  staff    85B Jan 16 17:18 Aimee-Maggio.user
-rw-r--r--    1 kidistwinters  staff    79B Jan 16 17:18 Alfonso-Gottlieb.user
-rw-r--r--    1 kidistwinters  staff   100B Jan 16 17:18 Allen-Kemmer.user
-rw-r--r--    1 kidistwinters  staff    86B Jan 16 17:18 Almina-Cormier.user
-rw-r--r--    1 kidistwinters  staff    87B Jan 16 17:18 Alta-Lemke.user
...
* Earlier, when you viewed the list of active processes on your devbox using `ps aux`, the list was probably really long. You can make this list more manageable by using the pipe (`|`) to filter the results of `ps` using `grep`. Run `ps aux | grep <your_username>` to see what processes are running for your specific user. *Paste the list of processes that reference your username here:*
...
kidistwinters     2651  11.1  5.9  6251292 246476   ??  S    10Jan19  41:59.69 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --type=renderer --js-flags=--nolazy --disable-mojo-local-storage --no-sandbox --disable-features=ColorCorrectRendering --service-pipe-token=994D00F641641DD075B337203FEDF258 --lang=en-US --app-path=/Applications/Visual Studio Code 4.app/Contents/Resources/app --node-integration=true --webview-tag=true --no-sandbox --background-color=#272822 --context-id=1 --enable-pinch --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,3553;0,11,34037;0,12,34037;0,13,34037;0,14,3553;0,15,3553;0,16,3553;0,17,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,3553;1,11,34037;1,12,34037;1,13,34037;1,14,3553;1,15,3553;1,16,3553;1,17,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,3553;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,3553;2,11,34037;2,12,34037;2,13,34037;2,14,3553;2,15,3553;2,16,3553;2,17,3553;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,3553;3,13,34037;3,14,34037;3,15,3553;3,16,34037;3,17,34037;4,0,3553;4,1,3553;4,2,3553;4,3,3553;4,4,3553;4,5,34037;4,6,3553;4,7,3553;4,8,3553;4,9,3553;4,10,3553;4,11,3553;4,12,3553;4,13,34037;4,14,34037;4,15,3553;4,16,34037;4,17,34037 --enable-gpu-async-worker-context --service-request-channel-token=994D00F641641DD075B337203FEDF258 --renderer-client-id=12
kidistwinters      965   6.4  0.9  4685916  38452   ??  S     8Jan19  20:48.55 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --type=gpu-process --disable-features=ColorCorrectRendering --no-sandbox --supports-dual-gpus=false --gpu-driver-bug-workarounds=0,1,12,27,30,43,47,56,62,70,73,74,75,76,83,84,86,94,95,96,100,103 --disable-gl-extensions=GL_KHR_blend_equation_advanced GL_KHR_blend_equation_advanced_coherent --gpu-vendor-id=0x8086 --gpu-device-id=0x0166 --gpu-driver-vendor --gpu-driver-version --gpu-driver-date --gpu-active-vendor-id=0x8086 --gpu-active-device-id=0x0166 --service-request-channel-token=DF489A5A7E2B88D292389788C885F514
kidistwinters      962   3.4  3.1  5963788 130612   ??  S     8Jan19  27:38.54 /Applications/Visual Studio Code 4.app/Contents/MacOS/Electron -psn_0_258111
kidistwinters      285   1.2  2.7  5322700 111408   ??  S     8Jan19  91:02.48 /Applications/Google Chrome.app/Contents/MacOS/Google Chrome -psn_0_45067
kidistwinters    16012   1.1  0.0  4270068    808 s001  S+    7:40PM   0:00.01 grep kidistwinters
kidistwinters    11747   0.4  1.2  5041524  51708   ??  S     5:23PM   4:40.95 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=7569703574912401155 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=7569703574912401155 --renderer-client-id=1148 --no-v8-untrusted-code-mitigations --seatbelt-client=213
kidistwinters    10959   0.4  0.3  4336808  14580   ??  S    Thu06PM   0:01.73 /System/Library/PrivateFrameworks/AppStoreDaemon.framework/Support/appstoreagent
kidistwinters     5417   0.3  0.5  4864228  19756   ??  S    13Jan19   3:22.77 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=625217935608892257 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=625217935608892257 --renderer-client-id=402 --no-v8-untrusted-code-mitigations --seatbelt-client=216
kidistwinters    11381   0.2  0.0  4296508   1104 s001  Ss    8:24AM   0:00.27 /bin/bash -l
kidistwinters     8585   0.2  0.9  4913256  36488   ??  S    Wed05PM   1:05.20 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=11328721596328054435 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=11328721596328054435 --renderer-client-id=1029 --no-v8-untrusted-code-mitigations --seatbelt-client=192
kidistwinters     7877   0.1  1.6  4847000  67888   ??  S    Tue07PM   1:05.66 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=744158564154841036 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=744158564154841036 --renderer-client-id=956 --no-v8-untrusted-code-mitigations --seatbelt-client=248
kidistwinters     8134   0.1  1.4  4916724  60420   ??  S    Wed03PM  10:12.91 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=8255368984463783725 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=8255368984463783725 --renderer-client-id=1020 --no-v8-untrusted-code-mitigations --seatbelt-client=225
kidistwinters     1037   0.1  0.3  5216120  14572   ??  S     8Jan19   0:11.98 /Users/kidistwinters/Desktop/Slack.app/Contents/Frameworks/Slack Helper.app/Contents/MacOS/Slack Helper --type=renderer --disable-pinch --force-color-profile=srgb --no-sandbox --service-pipe-token=278D2FB326AE34421DA9A79A2245CC4E --lang=en-US --standard-schemes=slack-resources,slack-sounds,slack-webapp-dev --secure-schemes=slack-resources,slack-sounds,slack-webapp-dev --app-path=/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar --node-integration=true--webview-tag=false --no-sandbox --preload=/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar/src/static/index.js --background-color=#FFFFFF --context-id=2 --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,3553;0,11,34037;0,12,34037;0,13,34037;0,14,3553;0,15,3553;0,16,3553;0,17,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,3553;1,11,34037;1,12,34037;1,13,34037;1,14,3553;1,15,3553;1,16,3553;1,17,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,3553;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,3553;2,11,34037;2,12,34037;2,13,34037;2,14,3553;2,15,3553;2,16,3553;2,17,3553;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,3553;3,13,34037;3,14,34037;3,15,3553;3,16,34037;3,17,34037;4,0,3553;4,1,3553;4,2,3553;4,3,3553;4,4,3553;4,5,34037;4,6,3553;4,7,3553;4,8,3553;4,9,3553;4,10,3553;4,11,3553;4,12,3553;4,13,34037;4,14,34037;4,15,3553;4,16,34037;4,17,34037 --enable-gpu-async-worker-context --service-request-channel-token=278D2FB326AE34421DA9A79A2245CC4E --renderer-client-id=8 {"loadSettings":{"resourcePath":"/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar","version":"3.3.3","devMode":false,"logFile":null,"invokedOnStartup":false,"chromeDriver":false,"webappSrcPath":null,"devEnv":null,"rxLogging":false,"sessionId":"NWRlY2ZhNDMtYTgwNS01NzM0LWEyZTItMTFkODM4NGY1ZmVhXzE1NDcwMDUwNTIwOTU=","releaseChannel":"prod","platformVersion":{"major":18,"minor":2,"build":0},"isTitleBarHidden":false,"isDevMode":false,"appVersion":"3.3.3","versionName":"Dirty Computer","webappParams":null,"launchOnStartup":false,"openDevToolsOnStart":false,"pretendNotReallyWindows10":false,"isAeroGlassEnabled":false,"isGpuCompositionAvailable":true,"webPreferences":{"webviewTag":false,"preload":"/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar/src/static/index.js"},"title":"Slack","autoHideMenuBar":false,"show":false,"windowType":"main","bootstrapScript":"/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar/src/renderer/main.tsx","acceptFirstMouse":false,"backgroundColor":"#FFFFFF","minHeight":400,"minWidth":600},"perfTimer":{"mainPid":293,"BOOT":[5438,324715986],"numTeamsAtLaunch":1,"SHELL":[5439,202923245],"APP_READY":[5447,497435208],"MAIN_WINDOW_CREATING":[5452,914524862]},"identifier":"slack_preload_metadata_arguments"}
kidistwinters    13566   0.0  0.1  4333568   5844   ??  S     6:39PM   0:00.11 /usr/libexec/swcd
kidistwinters    13390   0.0  0.2  4332448   9456   ??  S     6:29PM   0:00.10 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13350   0.0  0.2  4332448   9448   ??  S     6:27PM   0:00.09 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13298   0.0  0.2  4332448   9448   ??  S     6:25PM   0:00.06 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13282   0.0  0.4  4328200  17144   ??  S     6:24PM   0:00.74 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    13279   0.0  0.7  4322940  29496   ??  S     6:24PM   0:00.92 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    13277   0.0  0.6  4335384  24528   ??  S     6:24PM   0:00.56 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    13271   0.0  0.2  4332448   9444   ??  S     6:24PM   0:00.07 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13265   0.0  1.0  4797904  40400   ??  S     6:24PM   0:02.34 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=10679785909794951123 --lang=en-US --extension-process --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=10679785909794951123 --renderer-client-id=1196 --no-v8-untrusted-code-mitigations --seatbelt-client=192
kidistwinters    13227   0.0  0.2  4332448   9444   ??  S     6:03PM   0:00.08 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13192   0.0  0.2  4332448   9444   ??  S     6:01PM   0:00.06 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13190   0.0  0.2  4332448   9444   ??  S     6:00PM   0:00.07 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13171   0.0  0.2  4332448   9444   ??  S     5:59PM   0:00.07 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13145   0.0  0.2  4332448   9444   ??  S     5:58PM   0:00.09 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    13004   0.0  0.2  4332448   9444   ??  S     5:53PM   0:00.07 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    12657   0.0  0.2  4332448   9236   ??  S     5:46PM   0:00.08 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    12247   0.0  0.2  4332448   9232   ??  S     5:36PM   0:00.09 open -W http://127.0.0.1:5500/wats3020-sandwich-machine/index.html
kidistwinters    11754   0.0  0.3  4881036  11456   ??  S     5:24PM   0:00.61 /System/Library/CoreServices/OSDUIHelper.app/Contents/MacOS/OSDUIHelper
kidistwinters    11679   0.0  0.2  4332076   6948   ??  S     8:49AM   0:00.08 /System/Library/PrivateFrameworks/DistributedEvaluation.framework/Versions/A/XPCServices/com.apple.siri-distributed-evaluation.xpc/Contents/MacOS/com.apple.siri-distributed-evaluation
kidistwinters    11678   0.0  0.3  4358948  12680   ??  Ss    8:49AM   0:00.16 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Frameworks/PhotoLibraryServices.framework/Versions/A/XPCServices/com.apple.photomodel.xpc/Contents/MacOS/com.apple.photomodel
kidistwinters    11675   0.0  0.2  4305912   7508   ??  S     8:49AM   0:00.14 /usr/libexec/silhouette
kidistwinters    11607   0.0  0.1  4339532   4944   ??  S     8:49AM   0:00.13 /System/Library/PrivateFrameworks/ContextKit.framework/Versions/A/XPCServices/ContextService.xpc/Contents/MacOS/ContextService
kidistwinters    11598   0.0  0.3  4331200  13740   ??  S     8:48AM   0:00.13 /System/Library/PrivateFrameworks/PhotoAnalysis.framework/Versions/A/Support/photoanalysisd
kidistwinters    11597   0.0  0.4  4355244  15376   ??  Ss    8:48AM   0:00.67 /System/Library/Frameworks/MediaLibrary.framework/Versions/A/XPCServices/com.apple.MediaLibraryService.xpc/Contents/MacOS/com.apple.MediaLibraryService
kidistwinters    11592   0.0  0.1  4331408   5788   ??  S     8:47AM   0:00.06 /System/Library/PrivateFrameworks/QuickLookThumbnailing.framework/Support/com.apple.quicklook.ThumbnailsAgent
kidistwinters    11585   0.0  0.2  4305896   9592   ??  S     8:47AM   0:00.06 /System/Library/CoreServices/Software Update.app/Contents/Resources/softwareupdate_notify_agent
kidistwinters    11562   0.0  0.3  4334180  11404   ??  S     8:47AM   0:00.19 /System/Library/CoreServices/mapspushd
kidistwinters    11556   0.0  0.1  4334244   5900   ??  S     8:46AM   0:00.30 /System/Library/PrivateFrameworks/CacheDelete.framework/deleted
kidistwinters    11554   0.0  0.2  4332080   7672   ??  S     8:46AM   0:00.11 /System/Library/PrivateFrameworks/UsageTracking.framework/Versions/A/UsageTrackingAgent
kidistwinters    11542   0.0  0.3  4345580  12472   ??  S     8:40AM   0:00.60 /System/Library/CoreServices/CoreServicesUIAgent.app/Contents/MacOS/CoreServicesUIAgent
kidistwinters    11370   0.0  1.0  4997760  40432   ??  S     8:22AM   0:08.67 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=10176237069965901227 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=10176237069965901227 --renderer-client-id=1144 --no-v8-untrusted-code-mitigations --seatbelt-client=213
kidistwinters    11361   0.0  0.2  4297144   7496   ??  S     8:21AM   0:00.05 /System/Library/CoreServices/ReportCrash agent
kidistwinters    11359   0.0  0.3  4334392  13864   ??  S     8:18AM   0:00.26 /usr/libexec/fmfd
kidistwinters    11277   0.0  0.2  4331932   7780   ??  Ss   Sat12PM   0:00.17 /System/Library/PrivateFrameworks/FMClient.framework/Versions/A/XPCServices/FMIPClientXPCService.xpc/Contents/MacOS/FMIPClientXPCService
kidistwinters    11276   0.0  0.2  4332160   8032   ??  S    Sat12PM   0:00.14 /usr/libexec/siriknowledged
kidistwinters    11274   0.0  0.2  4307288   8844   ??  Ss   Sat12PM   0:00.23 /System/Library/Frameworks/iTunesLibrary.framework/Versions/A/XPCServices/com.apple.iTunesLibraryService.xpc/Contents/MacOS/com.apple.iTunesLibraryService
kidistwinters    11262   0.0  0.4  4399020  15900   ??  S    Sat12PM   0:01.66 /System/Library/PrivateFrameworks/AssistantServices.framework/Versions/A/Support/assistant_service
kidistwinters    11224   0.0  0.3  4335616  14560   ??  S    Sat12PM   0:00.83 /usr/libexec/adprivacyd
kidistwinters    11072   0.0  0.2  4333856   8632   ??  S    Thu06PM   0:00.27 /usr/libexec/networkserviceproxy
kidistwinters    11066   0.0  0.5  4694028  19548   ??  S    Thu06PM   0:01.16 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=ppapi --field-trial-handle=16176301987991042291,2925939690167536590,131072 --ppapi-flash-args --lang=en-US --service-request-channel-token=11134179637936289524 --seatbelt-client=192
kidistwinters    11064   0.0  0.8  4768956  35096   ??  S    Thu06PM   0:01.42 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=7055157738396199974 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=7055157738396199974 --renderer-client-id=1122 --no-v8-untrusted-code-mitigations --seatbelt-client=160
kidistwinters    11024   0.0  0.4  4337216  15420   ??  S    Thu06PM   0:05.07 /System/Library/CoreServices/SafariSupport.bundle/Contents/MacOS/SafariBookmarksSyncAgent
kidistwinters    10991   0.0  0.1  4332368   5304   ??  S    Thu06PM   0:00.34 /System/Library/CoreServices/pbs
kidistwinters    10990   0.0  0.2  4305176   7940   ??  Ss   Thu06PM   0:00.03 /System/Library/Frameworks/AudioToolbox.framework/XPCServices/com.apple.audio.SandboxHelper.xpc/Contents/MacOS/com.apple.audio.SandboxHelper
kidistwinters    10989   0.0  0.1  4304712   4284   ??  Ss   Thu06PM   0:00.14 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
kidistwinters    10983   0.0  0.2  4331904   9088   ??  S    Thu06PM   0:00.32 /System/Library/Frameworks/LocalAuthentication.framework/Support/coreauthd
kidistwinters    10974   0.0  0.2  4344212   7284   ??  S    Thu06PM   0:03.63 /System/Library/CoreServices/iconservicesagent
kidistwinters    10958   0.0  0.2  4332608   9640   ??  Ss   Thu06PM   0:00.38 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
kidistwinters    10942   0.0  0.3  4331800  12868   ??  Ss   Thu09AM   0:00.07 /System/Library/PrivateFrameworks/PhotoLibrary.framework/Versions/A/XPCServices/com.apple.PhotoIngestService.xpc/Contents/MacOS/com.apple.PhotoIngestService
kidistwinters    10941   0.0  0.3  4331240  12836   ??  Ss   Thu09AM   0:00.08 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Frameworks/PhotoLibraryServices.framework/Versions/A/XPCServices/com.apple.photomoments.xpc/Contents/MacOS/com.apple.photomoments
kidistwinters    10937   0.0  0.2  4338576   8704   ??  S    Thu09AM   0:01.42 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistoryPluginHelper
kidistwinters    10934   0.0  0.2  4307288   8764   ??  Ss   Thu09AM   0:00.29 /System/Library/Frameworks/iTunesLibrary.framework/Versions/A/XPCServices/com.apple.iTunesLibraryService.xpc/Contents/MacOS/com.apple.iTunesLibraryService
kidistwinters    10932   0.0  0.4  4345156  15132   ??  S    Thu09AM   0:06.31 /System/Library/PrivateFrameworks/TelephonyUtilities.framework/callservicesd
kidistwinters    10931   0.0  0.3  4412032  10532   ??  Ss   Thu09AM   0:00.33 /System/Library/PrivateFrameworks/AssistantServices.framework/Versions/A/XPCServices/media-indexer.xpc/Contents/MacOS/media-indexer
kidistwinters    10930   0.0  0.1  4333180   5108   ??  S    Thu09AM   0:00.33 /System/Library/Frameworks/AudioToolbox.framework/AudioComponentRegistrar
kidistwinters    10923   0.0  0.3  4358512  13572   ??  S    Thu09AM   0:00.38 /System/Library/PrivateFrameworks/CloudPhotoServices.framework/Versions/A/Frameworks/CloudPhotosConfigurationXPC.framework/Versions/A/XPCServices/com.apple.CloudPhotosConfiguration.xpc/Contents/MacOS/com.apple.CloudPhotosConfiguration
kidistwinters    10914   0.0  0.3  4341376  13348   ??  S    Thu09AM   0:03.72 /System/Library/PrivateFrameworks/CallHistory.framework/Support/CallHistorySyncHelper
kidistwinters    10912   0.0  0.4  4396656  16312   ??  S    Thu09AM   0:04.82 /System/Library/CoreServices/cloudphotosd.app/Contents/MacOS/cloudphotosd
kidistwinters    10911   0.0  0.2  4339520   8680   ??  S    Thu09AM   0:02.12 /usr/libexec/knowledge-agent
kidistwinters    10527   0.0  0.3  4312564  10860   ??  S    Thu08AM   0:00.60 /System/Library/PrivateFrameworks/IMDPersistence.framework/XPCServices/IMDPersistenceAgent.xpc/Contents/MacOS/IMDPersistenceAgent
kidistwinters    10525   0.0  0.4  4422844  16448   ??  S    Thu08AM   0:06.45 /System/Library/PrivateFrameworks/CoreSuggestions.framework/Versions/A/Support/suggestd
kidistwinters    10498   0.0  0.1  4297636   4872   ??  S    Thu08AM   0:00.14 /usr/libexec/spindump_agent
kidistwinters    10497   0.0  0.4  4341752  15920   ??  Ss   Thu08AM   0:06.65 /System/Library/PrivateFrameworks/CalendarNotification.framework/Versions/A/XPCServices/CalNCService.xpc/Contents/MacOS/CalNCService
kidistwinters    10494   0.0  0.2  4304836   8012   ??  S    Thu08AM   0:00.10 /System/Library/PrivateFrameworks/CoreFollowUp.framework/Versions/A/Support/followupd
kidistwinters    10492   0.0  0.4  4854500  16468   ??  Ss   Thu08AM   0:02.95 /System/Library/CoreServices/Siri.app/Contents/XPCServices/SiriNCService.xpc/Contents/MacOS/SiriNCService
kidistwinters    10491   0.0  0.4  4358336  16452   ??  S    Thu08AM   0:03.59 /System/Library/PrivateFrameworks/AssistantServices.framework/Versions/A/Support/assistantd
kidistwinters    10490   0.0  0.2  4350232   7844   ??  S    Thu08AM   0:01.86 /System/Library/PrivateFrameworks/GeoServices.framework/Versions/A/XPCServices/com.apple.geod.xpc/Contents/MacOS/com.apple.geod
kidistwinters    10484   0.0  0.3  4338588  10812   ??  S    Thu08AM   0:01.13 /System/Library/CoreServices/talagent
kidistwinters    10482   0.0  0.3  4338536  13384   ??  S    Wed09PM   0:01.76 /System/Library/PrivateFrameworks/CloudServices.framework/Versions/A/XPCServices/com.apple.sbd.xpc/Contents/MacOS/com.apple.sbd
kidistwinters    10481   0.0  0.2  4334012   6312   ??  S    Wed09PM   0:01.73 /usr/libexec/nsurlstoraged
kidistwinters    10479   0.0  0.2  4332132  10028   ??  S    Wed09PM   0:02.68 /System/Library/PrivateFrameworks/ViewBridge.framework/Versions/A/XPCServices/ViewBridgeAuxiliary.xpc/Contents/MacOS/ViewBridgeAuxiliary
kidistwinters    10476   0.0  0.2  4339120   8016   ??  S    Wed09PM   0:01.82 /System/Library/PrivateFrameworks/AuthKit.framework/Versions/A/Support/akd
kidistwinters    10475   0.0  0.2  4338412   6564   ??  S    Wed09PM   0:00.77 /System/Library/PrivateFrameworks/AssetCacheServices.framework/Versions/A/XPCServices/AssetCacheLocatorService.xpc/Contents/MacOS/AssetCacheLocatorService -a
kidistwinters    10474   0.0  0.3  4304708  12988   ??  S    Wed09PM   0:01.15 /System/Library/Frameworks/AddressBook.framework/Executables/ContactsAccountsService
kidistwinters    10473   0.0  0.1  4333396   5584   ??  S    Wed09PM   0:00.52 /usr/libexec/secinitd
kidistwinters    10472   0.0  0.4  4340260  15324   ??  S    Wed09PM   0:05.22 /System/Library/PrivateFrameworks/MessagesKit.framework/Resources/soagent.app/Contents/MacOS/soagent
kidistwinters    10469   0.0  0.2  4306452   7936   ??  S    Wed09PM   0:00.05 /System/Library/Frameworks/CryptoTokenKit.framework/ctkd -tw
kidistwinters    10468   0.0  0.2  4306008   7924   ??  S    Wed09PM   0:00.07 /System/Library/Frameworks/CryptoTokenKit.framework/ctkahp.bundle/Contents/MacOS/ctkahp
kidistwinters    10462   0.0  0.2  4351288   9200   ??  S    Wed09PM   0:14.89 /usr/libexec/trustd --agent
kidistwinters    10457   0.0  0.1  4306420   5816   ??  S    Wed09PM   0:01.85 /System/Library/Frameworks/Security.framework/Versions/A/Resources/CloudKeychainProxy.bundle/Contents/MacOS/CloudKeychainProxy
kidistwinters    10455   0.0  0.3  4304712  14652   ??  S    Wed09PM   0:00.13 /System/Library/CoreServices/EscrowSecurityAlert.app/Contents/MacOS/EscrowSecurityAlert
kidistwinters    10454   0.0  0.3  4331876  11860   ??  S    Wed09PM   0:00.26 /System/Library/PrivateFrameworks/ProtectedCloudStorage.framework/Helpers/ProtectedCloudKeySyncing
kidistwinters    10453   0.0  0.2  4304656   7160   ??  S    Wed09PM   0:00.15 /System/Library/PrivateFrameworks/CoreCDP.framework/Versions/A/Resources/cdpd
kidistwinters    10445   0.0  0.5  4391536  22844   ??  S    Wed09PM   0:18.87 /System/Library/Frameworks/Accounts.framework/Versions/A/Support/accountsd
kidistwinters    10444   0.0  0.2  4336892   6668   ??  S    Wed09PM   0:00.97 /System/Library/PrivateFrameworks/TCC.framework/Resources/tccd
kidistwinters    10443   0.0  0.6  4349224  23484   ??  S    Wed09PM   0:08.79 /System/Library/PrivateFrameworks/CloudKitDaemon.framework/Support/cloudd
kidistwinters    10441   0.0  0.4  4341312  17076   ??  S    Wed09PM   0:32.41 /usr/libexec/secd
kidistwinters    10440   0.0  0.4  4338376  16416   ??  S    Wed09PM   0:00.92 /System/Library/CoreServices/Keychain Circle Notification.app/Contents/MacOS/Keychain Circle Notification
kidistwinters    10429   0.0  0.4  4342228  16132   ??  S    Wed09PM   0:03.16 /System/Library/CoreServices/Siri.app/Contents/MacOS/Siri launchd
kidistwinters    10410   0.0  0.4  4340956  16932   ??  S    Wed09PM   0:03.37 /usr/libexec/routined LAUNCHED_BY_LAUNCHD
kidistwinters    10374   0.0  0.0  4296508    488 s004  Ss+  Wed08PM   0:00.10 /bin/bash -l
kidistwinters    10231   0.0  0.1  4332484   4744   ??  S<   Wed08PM   0:00.07 /Users/kidistwinters/Desktop/Slack.app/Contents/Frameworks/Squirrel.framework/Resources/ShipIt com.tinyspeck.slackmacgap.ShipIt /Users/kidistwinters/Library/Caches/com.tinyspeck.slackmacgap.ShipIt/ShipItState.plist
kidistwinters    10192   0.0  0.0  4288316    244 s003  Ss+  Wed07PM   0:00.08 /bin/bash -l
kidistwinters    10030   0.0  0.0  4277236    168 s002  S+   Wed07PM   0:00.01 grep .user
kidistwinters     9203   0.0  0.0  4296508    184 s002  Ss   Wed06PM   0:00.12 /bin/bash -l
kidistwinters     8589   0.0  0.6  4752480  23436   ??  S    Wed05PM   0:00.77 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=9743368773008338363 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=9743368773008338363 --renderer-client-id=1033 --no-v8-untrusted-code-mitigations --seatbelt-client=239
kidistwinters     8588   0.0  0.6  4764244  23632   ??  S    Wed05PM   0:01.83 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=15282748792593574635 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=15282748792593574635 --renderer-client-id=1032 --no-v8-untrusted-code-mitigations --seatbelt-client=225
kidistwinters     8587   0.0  0.7  4824096  27268   ??  S    Wed05PM   0:11.35 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=1633499766214481430 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=1633499766214481430 --renderer-client-id=1031 --no-v8-untrusted-code-mitigations --seatbelt-client=214
kidistwinters     8586   0.0  0.6  4754652  24024   ??  S    Wed05PM   0:26.67 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=4197800847040951096 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=4197800847040951096 --renderer-client-id=1030 --no-v8-untrusted-code-mitigations --seatbelt-client=214
kidistwinters     8303   0.0  0.3  5078436  11800   ??  S    Wed04PM   1:13.33 /Applications/Utilities/Terminal.app/Contents/MacOS/Terminal
kidistwinters     8136   0.0  0.6  4767080  24772   ??  S    Wed03PM   0:02.84 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=16132673820565105503 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=16132673820565105503 --renderer-client-id=1022 --no-v8-untrusted-code-mitigations --seatbelt-client=212
kidistwinters     8135   0.0  0.6  4752468  25328   ??  S    Wed03PM   0:02.26 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=6523039715197865554 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=6523039715197865554 --renderer-client-id=1021 --no-v8-untrusted-code-mitigations --seatbelt-client=223
kidistwinters     8123   0.0  0.7  4872628  30564   ??  S    Wed03PM   0:20.97 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=2853146401191921063 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=2853146401191921063 --renderer-client-id=1016 --no-v8-untrusted-code-mitigations --seatbelt-client=193
kidistwinters     8032   0.0  0.7  4855452  29028   ??  S    Wed02PM  10:23.79 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=10426360953896954322 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=10426360953896954322 --renderer-client-id=977 --no-v8-untrusted-code-mitigations --seatbelt-client=188
kidistwinters     8005   0.0  0.7  4984232  30684   ??  S    Wed02PM   0:10.51 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=9272014751820851485 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=9272014751820851485 --renderer-client-id=965 --no-v8-untrusted-code-mitigations --seatbelt-client=209
kidistwinters     7880   0.0  0.6  4751952  23768   ??  S    Tue07PM   0:01.53 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=7970739245677350639 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=7970739245677350639 --renderer-client-id=959 --no-v8-untrusted-code-mitigations --seatbelt-client=281
kidistwinters     7879   0.0  0.6  4752352  23128   ??  S    Tue07PM   0:00.96 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=5146532736006534318 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=5146532736006534318 --renderer-client-id=958 --no-v8-untrusted-code-mitigations --seatbelt-client=277
kidistwinters     7878   0.0  0.6  4759464  25292   ??  S    Tue07PM   0:01.10 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=7704758430985152019 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=7704758430985152019 --renderer-client-id=957 --no-v8-untrusted-code-mitigations --seatbelt-client=256
kidistwinters     7876   0.0  1.0  5065592  40736   ??  S    Tue07PM   1:34.28 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=14587983858960216173 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=14587983858960216173 --renderer-client-id=955 --no-v8-untrusted-code-mitigations --seatbelt-client=199
kidistwinters     7841   0.0  1.0  4989872  43664   ??  S    Tue06PM   6:27.51 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=14205724402788773669 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=14205724402788773669 --renderer-client-id=922 --no-v8-untrusted-code-mitigations --seatbelt-client=177
kidistwinters     7775   0.0  0.1  4332448   4736   ??  S    Tue06PM   0:00.10 open -W http://127.0.0.1:5500/wats3020/wats3020-mad-libs/index.html
kidistwinters     7625   0.0  0.6  4769000  25204   ??  S    Tue06PM   0:01.38 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=renderer --field-trial-handle=16176301987991042291,2925939690167536590,131072 --service-pipe-token=13029444887090685440 --lang=en-US --enable-offline-auto-reload --enable-offline-auto-reload-visible-only--num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --service-request-channel-token=13029444887090685440 --renderer-client-id=901 --no-v8-untrusted-code-mitigations --seatbelt-client=200
kidistwinters     6900   0.0  0.0  4332448    140   ??  S    13Jan19   0:00.10 open -W http://127.0.0.1:5500/wats3020/wats3020-mad-libs/index.html
kidistwinters     5777   0.0  0.0  4332448    140   ??  S    13Jan19   0:00.12 open -W http://127.0.0.1:5500/wats3020/wats3020-mad-libs/index.html
kidistwinters     5319   0.0  0.1  5017496   4616   ??  S    13Jan19   0:05.16 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/Visual Studio Code 4.app/Contents/Resources/app/extensions/css-language-features/server/dist/cssServerMain --node-ipc --clientProcessId=2653
kidistwinters     5006   0.0  0.0  4332448    140   ??  S    13Jan19   0:00.10 open -W http://127.0.0.1:5500/wats3020/wats3020-mad-libs/index.html
kidistwinters     4490   0.0  2.5  5839544 103144   ??  S    13Jan19   4:41.51 /Users/kidistwinters/Desktop/Slack.app/Contents/Frameworks/Slack Helper.app/Contents/MacOS/Slack Helper --type=renderer --disable-pinch --force-color-profile=srgb --no-sandbox --service-pipe-token=EEB759EF8C3CB4F86CA86A8457A77EEB --lang=en-US --standard-schemes=slack-resources,slack-sounds,slack-webapp-dev --secure-schemes=slack-resources,slack-sounds,slack-webapp-dev --app-path=/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar --enable-experimental-web-platform-features --node-integration=false --webview-tag=false --no-sandbox --preload=/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar/src/static/ssb-interop.js --context-id=1 --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,3553;0,11,34037;0,12,34037;0,13,34037;0,14,3553;0,15,3553;0,16,3553;0,17,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,3553;1,11,34037;1,12,34037;1,13,34037;1,14,3553;1,15,3553;1,16,3553;1,17,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,3553;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,3553;2,11,34037;2,12,34037;2,13,34037;2,14,3553;2,15,3553;2,16,3553;2,17,3553;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,3553;3,13,34037;3,14,34037;3,15,3553;3,16,34037;3,17,34037;4,0,3553;4,1,3553;4,2,3553;4,3,3553;4,4,3553;4,5,34037;4,6,3553;4,7,3553;4,8,3553;4,9,3553;4,10,3553;4,11,3553;4,12,3553;4,13,34037;4,14,34037;4,15,3553;4,16,34037;4,17,34037 --enable-gpu-async-worker-context --service-request-channel-token=EEB759EF8C3CB4F86CA86A8457A77EEB --renderer-client-id=9 {"loadSettings":{"resourcePath":"/Users/kidistwinters/Desktop/Slack.app/Contents/Resources/app.asar","version":"3.3.3","devMode":false,"logFile":null,"invokedOnStartup":false,"chromeDriver":false,"webappSrcPath":null,"devEnv":null,"rxLogging":false,"sessionId":"NWRlY2ZhNDMtYTgwNS01NzM0LWEyZTItMTFkODM4NGY1ZmVhXzE1NDcwMDUwNTIwOTU=","releaseChannel":"prod","platformVersion":{"major":18,"minor":2,"build":0},"isTitleBarHidden":false,"isDevMode":false,"appVersion":"3.3.3","versionName":"Dirty Computer","webappParams":null,"launchOnStartup":false,"openDevToolsOnStart":false,"pretendNotReallyWindows10":false,"isAeroGlassEnabled":false,"isGpuCompositionAvailable":true,"windowType":"webapp","subType":"T03ANFNQR-preload"},"perfTimer":{"mainPid":293,"BOOT":[5438,324715986],"numTeamsAtLaunch":1,"SHELL":[5439,202923245],"APP_READY":[5447,497435208],"MAIN_WINDOW_CREATING":[5452,914524862]},"identifier":"slack_preload_metadata_arguments","teamId":"T03ANFNQR"}
kidistwinters     3535   0.0  0.0  4304660    420   ??  S    13Jan19   0:00.12 /System/Library/PrivateFrameworks/MediaRemote.framework/Support/mediaremoteagent
kidistwinters     3382   0.0  0.0  4365516   1796   ??  S    13Jan19   0:01.53 /System/Library/PrivateFrameworks/PhotoLibraryPrivate.framework/Versions/A/Support/photolibraryd
kidistwinters     3138   0.0  0.0  4332448    136   ??  S    10Jan19   0:00.13 open -W http://127.0.0.1:5500/wats3020/wats3020-mad-libs/index.html
kidistwinters     2891   0.0  0.0  4296508    104 s000  Ss+  10Jan19   0:00.23 /bin/bash -l
kidistwinters     2886   0.0  0.0  4296960    152   ??  S    10Jan19   0:00.03 /System/Library/PrivateFrameworks/KerberosHelper/Helpers/DiskUnmountWatcher
kidistwinters     2835   0.0  0.1  4858252   2852   ??  S    10Jan19   0:04.08 /System/Library/PrivateFrameworks/UniversalAccess.framework/Versions/A/Resources/universalAccessAuthWarn.app/Contents/MacOS/universalAccessAuthWarn launchd -s
kidistwinters     2779   0.0  0.1  5062604   2336   ??  S    10Jan19   1:32.06 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/Visual Studio Code 4.app/Contents/Resources/app/extensions/node_modules/typescript/lib/typingsInstaller.js --globalTypingsCacheLocation /Users/kidistwinters/Library/Caches/typescript/3.2 --enableTelemetry --typesMapLocation /Applications/Visual Studio Code 4.app/Contents/Resources/app/extensions/node_modules/typescript/lib/typesMap.json
kidistwinters     2775   0.0  0.3  5140640  10516   ??  S    10Jan19   2:03.73 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/Visual Studio Code 4.app/Contents/Resources/app/extensions/node_modules/typescript/lib/tsserver.js --useInferredProjectPerProjectRoot --enableTelemetry --cancellationPipeName /var/folders/4x/0cspcc492zx6zbgfxg_pwxwh0000gp/T/vscode-typescript/tscancellation-4a2070561f2ef0ace69a.tmp* --locale en --noGetErrOnBackgroundUpdate
kidistwinters     2774   0.0  0.1  5008488   4180   ??  S    10Jan19   0:05.22 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Users/kidistwinters/.vscode/extensions/dbaeumer.vscode-eslint-1.8.0/server/out/eslintServer.js --node-ipc --clientProcessId=2653
kidistwinters     2767   0.0  0.0  4332448    116   ??  S    10Jan19   0:00.11 open -W http://127.0.0.1:5500/wats3020/wats3020-mad-libs/index.html
kidistwinters     2726   0.0  0.0  4332448    116   ??  S    10Jan19   0:00.10 open -W http://127.0.0.1:5500/wats3010-intro-to-bootstrap-4/index.html
kidistwinters     2724   0.0  0.1  5036884   4244   ??  S    10Jan19   0:06.09 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/Visual Studio Code 4.app/Contents/Resources/app/extensions/html-language-features/server/dist/htmlServerMain --node-ipc --clientProcessId=2653
kidistwinters     2653   0.0  1.7  5168808  70136   ??  S    10Jan19   1:56.66 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --nolazy --inspect=55543 /Applications/Visual Studio Code 4.app/Contents/Resources/app/out/bootstrap-fork --type=extensionHost
kidistwinters     2652   0.0  0.2  5047468   7220   ??  S    10Jan19   0:05.76 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper /Applications/Visual Studio Code 4.app/Contents/Resources/app/out/bootstrap-fork --type=watcherService
kidistwinters     2532   0.0  0.1  4336564   2984   ??  S    10Jan19   0:03.17 /System/Library/PrivateFrameworks/PassKitCore.framework/passd
kidistwinters     2531   0.0  0.1  4337036   4796   ??  S    10Jan19   0:11.10 /System/Library/PrivateFrameworks/HomeKitDaemon.framework/Support/homed
kidistwinters     2435   0.0  0.1  4332608   2104   ??  Ss   10Jan19   0:00.98 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
kidistwinters     2433   0.0  0.1  4335660   2604   ??  S    10Jan19   0:00.99 /usr/libexec/avconferenced
kidistwinters     2415   0.0  0.0  4305320    208   ??  S    10Jan19   0:00.10 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdwrite
kidistwinters     2198   0.0  0.1  4339052   2960   ??  S     9Jan19   0:02.28 /usr/libexec/keyboardservicesd
kidistwinters     2057   0.0  0.6  4608228  26032   ??  S     9Jan19   0:31.19 /System/Library/Services/AppleSpell.service/Contents/MacOS/AppleSpell
kidistwinters     1728   0.0  0.0  4332448    116   ??  S     9Jan19   0:00.10 open -W http://127.0.0.1:5500/index.html
kidistwinters     1077   0.0  0.0  4340520    268   ??  S     8Jan19   0:01.36 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/SpeechSynthesis.framework/Resources/com.apple.speech.speechsynthesisd
kidistwinters     1059   0.0  0.0  4289444     24   ??  S     8Jan19   0:00.07 /usr/bin/ssh-agent -l
kidistwinters     1035   0.0  0.0  4307588    556   ??  S     8Jan19   0:00.19 /Users/kidistwinters/Desktop/Slack.app/Contents/Frameworks/Electron Framework.framework/Resources/crashpad_handler --no-rate-limit --no-upload-gzip --database=/var/folders/4x/0cspcc492zx6zbgfxg_pwxwh0000gp/T/Slack Crashes --metrics-dir=/var/folders/4x/0cspcc492zx6zbgfxg_pwxwh0000gp/T/Slack Crashes --url=https://slack.com/apps/breakpad?instanceUid=5decfa43-a805-5734-a2e2-11d8384f5fea&version=3.3.3&channel=prod --handshake-fd=49
kidistwinters     1031   0.0  0.1  4593980   2452   ??  S     8Jan19   0:58.42 /Users/kidistwinters/Desktop/Slack.app/Contents/Frameworks/Slack Helper.app/Contents/MacOS/Slack Helper --type=gpu-process --no-sandbox --supports-dual-gpus=false --gpu-driver-bug-workarounds=0,1,12,27,30,43,47,56,62,70,73,74,75,76,83,84,86,94,95,96,100,103 --disable-gl-extensions=GL_KHR_blend_equation_advanced GL_KHR_blend_equation_advanced_coherent --gpu-vendor-id=0x8086 --gpu-device-id=0x0166 --gpu-driver-vendor --gpu-driver-version --gpu-driver-date --gpu-active-vendor-id=0x8086 --gpu-active-device-id=0x0166 --service-request-channel-token=329780D01D18116AC6F39B682B927163
kidistwinters      973   0.0  0.0  4307628    276   ??  S     8Jan19   0:00.18 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Electron Framework.framework/Resources/crashpad_handler --no-rate-limit --no-upload-gzip --database=/var/folders/4x/0cspcc492zx6zbgfxg_pwxwh0000gp/T/VSCode Crashes --metrics-dir=/var/folders/4x/0cspcc492zx6zbgfxg_pwxwh0000gp/T/VSCode Crashes --url=https://rink.hockeyapp.net/api/2/apps/21a48a66799e47fea4f52c0ff81e803d/crashes/upload --handshake-fd=62
kidistwinters      971   0.0  0.4  5190600  18080   ??  S     8Jan19   0:36.27 /Applications/Visual Studio Code 4.app/Contents/Frameworks/Code Helper.app/Contents/MacOS/Code Helper --type=renderer --js-flags=--nolazy --disable-mojo-local-storage --no-sandbox --disable-features=ColorCorrectRendering --service-pipe-token=11A9EF8DC9034A85A1639E3334E73C54 --lang=en-US --app-path=/Applications/Visual Studio Code 4.app/Contents/Resources/app --node-integration=true --webview-tag=true --no-sandbox --background-color=#272822 --disable-blink-features=Auxclick --context-id=2 --enable-pinch --num-raster-threads=2 --enable-zero-copy --enable-gpu-memory-buffer-compositor-resources --enable-main-frame-before-activation --content-image-texture-target=0,0,3553;0,1,3553;0,2,3553;0,3,3553;0,4,3553;0,5,3553;0,6,3553;0,7,3553;0,8,3553;0,9,3553;0,10,3553;0,11,34037;0,12,34037;0,13,34037;0,14,3553;0,15,3553;0,16,3553;0,17,3553;1,0,3553;1,1,3553;1,2,3553;1,3,3553;1,4,3553;1,5,3553;1,6,3553;1,7,3553;1,8,3553;1,9,3553;1,10,3553;1,11,34037;1,12,34037;1,13,34037;1,14,3553;1,15,3553;1,16,3553;1,17,3553;2,0,3553;2,1,3553;2,2,3553;2,3,3553;2,4,3553;2,5,3553;2,6,3553;2,7,3553;2,8,3553;2,9,3553;2,10,3553;2,11,34037;2,12,34037;2,13,34037;2,14,3553;2,15,3553;2,16,3553;2,17,3553;3,0,3553;3,1,3553;3,2,3553;3,3,3553;3,4,3553;3,5,34037;3,6,3553;3,7,3553;3,8,3553;3,9,3553;3,10,3553;3,11,3553;3,12,3553;3,13,34037;3,14,34037;3,15,3553;3,16,34037;3,17,34037;4,0,3553;4,1,3553;4,2,3553;4,3,3553;4,4,3553;4,5,34037;4,6,3553;4,7,3553;4,8,3553;4,9,3553;4,10,3553;4,11,3553;4,12,3553;4,13,34037;4,14,34037;4,15,3553;4,16,34037;4,17,34037 --enable-gpu-async-worker-context --service-request-channel-token=11A9EF8DC9034A85A1639E3334E73C54 --renderer-client-id=6
kidistwinters      953   0.0  0.0  4304992    868   ??  S     8Jan19   0:00.64 /usr/libexec/assertiond
kidistwinters      872   0.0  0.0  4333412    464   ??  S     8Jan19   0:03.23 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker -s mdworker-sizing -c MDSSizingWorker -m com.apple.mdworker.sizing
kidistwinters      689   0.0  0.0  4332016   1468   ??  S     8Jan19   0:00.62 /System/Library/PrivateFrameworks/IMDPersistence.framework/IMAutomaticHistoryDeletionAgent.app/Contents/MacOS/IMAutomaticHistoryDeletionAgent
kidistwinters      679   0.0  0.0  4334692   1320   ??  S     8Jan19   0:00.37 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storedownloadd
kidistwinters      631   0.0  0.1  4635124   2160   ??  S     8Jan19   0:05.82 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/corespotlightd
kidistwinters      602   0.0  0.0  4304832    340   ??  S     8Jan19   0:00.14 /usr/libexec/mobileactivationd
kidistwinters      478   0.0  0.1  4342172   2940   ??  S     8Jan19   0:04.16 /System/Library/PrivateFrameworks/CommerceKit.framework/Resources/LaterAgent.app/Contents/MacOS/LaterAgent
kidistwinters      475   0.0  0.1  4375108   4808   ??  S     8Jan19   0:10.08 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeassetd
kidistwinters      473   0.0  0.0  4333000    216   ??  S     8Jan19   0:00.16 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storelegacy
kidistwinters      461   0.0  0.0  4332180   2028   ??  S     8Jan19   0:00.54 /System/Library/PrivateFrameworks/FileProvider.framework/Support/fileproviderd
kidistwinters      441   0.0  0.1  4342440   3040   ??  S     8Jan19   0:04.51 com.GoPro.goproapp-devicedetection
kidistwinters      440   0.0  0.1  4333148   2616   ??  S     8Jan19   0:03.04 /System/Library/CoreServices/diagnostics_agent
kidistwinters      439   0.0  0.1  4347820   4132   ??  S     8Jan19   0:08.00 /System/Library/PrivateFrameworks/Noticeboard.framework/Versions/A/Resources/nbagent.app/Contents/MacOS/nbagent
kidistwinters      438   0.0  0.0  4333064    956   ??  S     8Jan19   0:02.97 /System/Library/CoreServices/cloudpaird
kidistwinters      436   0.0  0.1  4854472   2360   ??  S     8Jan19   0:05.17 /System/Library/CoreServices/AirPlayUIAgent.app/Contents/MacOS/AirPlayUIAgent --launchd
kidistwinters      432   0.0  0.0  4336036   1296   ??  S     8Jan19   0:02.19 /System/Library/Image Capture/Support/icdd
kidistwinters      427   0.0  0.0  4331312    596   ??  S     8Jan19   0:00.37 /System/Library/CoreServices/SocialPushAgent.app/Contents/MacOS/SocialPushAgent
kidistwinters      424   0.0  0.0  4304756    160   ??  S     8Jan19   0:00.11 /System/Library/PrivateFrameworks/CoreSpeech.framework/corespeechd
kidistwinters      423   0.0  0.1  4858376   3376   ??  Ss    8Jan19   0:09.91 /System/Library/Input Methods/PressAndHold.app/Contents/PlugIns/PAH_Extension.appex/Contents/MacOS/PAH_Extension
kidistwinters      422   0.0  0.1  4334900   3196   ??  S     8Jan19   0:03.08 /System/Library/Frameworks/InputMethodKit.framework/Resources/imklaunchagent
kidistwinters      396   0.0  0.1  4335240   2732   ??  Ss    8Jan19   0:02.82 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
kidistwinters      395   0.0  0.1  4332624   2196   ??  Ss    8Jan19   0:01.24 /System/Library/PrivateFrameworks/IMFoundation.framework/XPCServices/IMRemoteURLConnectionAgent.xpc/Contents/MacOS/IMRemoteURLConnectionAgent
kidistwinters      377   0.0  0.1  4542148   3888   ??  S     8Jan19   0:20.59 /System/Library/CoreServices/WiFiAgent.app/Contents/MacOS/WiFiAgent
kidistwinters      374   0.0  0.1  4346584   3084   ??  S     8Jan19   0:05.22 /System/Library/CoreServices/CoreLocationAgent.app/Contents/MacOS/CoreLocationAgent
kidistwinters      371   0.0  0.2  4369052   8384   ??  S     8Jan19   1:14.97 /System/Library/PrivateFrameworks/CalendarAgent.framework/Executables/CalendarAgent
kidistwinters      368   0.0  0.0  4306452   1388   ??  S     8Jan19   0:00.47 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/storeaccountd
kidistwinters      364   0.0  0.1  4332960   2532   ??  Ss    8Jan19   0:05.63 /System/Library/PrivateFrameworks/CoreWLANKit.framework/Versions/A/XPCServices/WiFiProxy.xpc/Contents/MacOS/WiFiProxy
kidistwinters      363   0.0  0.4  4763988  18260   ??  S     8Jan19  35:20.89 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Helper.app/Contents/MacOS/Google Chrome Helper --type=gpu-process --field-trial-handle=16176301987991042291,2925939690167536590,131072 --gpu-preferences=KAAAAAAAAACAAAAAAQAAAAAAAAAAAGAAAAAAAAAAAAAIAAAAAAAAADgBAAAmAAAAMAEAAAAAAAA4AQAAAAAAAEABAAAAAAAASAEAAAAAAABQAQAAAAAAAFgBAAAAAAAAYAEAAAAAAABoAQAAAAAAAHABAAAAAAAAeAEAAAAAAACAAQAAAAAAAIgBAAAAAAAAkAEAAAAAAACYAQAAAAAAAKABAAAAAAAAqAEAAAAAAACwAQAAAAAAALgBAAAAAAAAwAEAAAAAAADIAQAAAAAAANABAAAAAAAA2AEAAAAAAADgAQAAAAAAAOgBAAAAAAAA8AEAAAAAAAD4AQAAAAAAAAACAAAAAAAACAIAAAAAAAAQAgAAAAAAABgCAAAAAAAAIAIAAAAAAAAoAgAAAAAAADACAAAAAAAAOAIAAAAAAABAAgAAAAAAAEgCAAAAAAAAUAIAAAAAAABYAgAAAAAAABAAAAAAAAAAAAAAAAAAAAAQAAAAAAAAAAAAAAAGAAAAEAAAAAAAAAAAAAAABwAAABAAAAAAAAAAAAAAAAgAAAAQAAAAAAAAAAAAAAAKAAAAEAAAAAAAAAAAAAAACwAAABAAAAAAAAAAAAAAAA0AAAAQAAAAAAAAAAAAAAAOAAAAEAAAAAAAAAABAAAAAAAAABAAAAAAAAAAAQAAAAYAAAAQAAAAAAAAAAEAAAAHAAAAEAAAAAAAAAABAAAACAAAABAAAAAAAAAAAQAAAAoAAAAQAAAAAAAAAAEAAAALAAAAEAAAAAAAAAABAAAADQAAABAAAAAAAAAAAQAAAA4AAAAQAAAAAAAAAAQAAAAAAAAAEAAAAAAAAAAEAAAABgAAABAAAAAAAAAABAAAAAcAAAAQAAAAAAAAAAQAAAAIAAAAEAAAAAAAAAAEAAAACgAAABAAAAAAAAAABAAAAAsAAAAQAAAAAAAAAAQAAAANAAAAEAAAAAAAAAAEAAAADgAAABAAAAAAAAAABgAAAAAAAAAQAAAAAAAAAAYAAAAGAAAAEAAAAAAAAAAGAAAACAAAABAAAAAAAAAABgAAAAoAAAAQAAAAAAAAAAYAAAALAAAAEAAAAAAAAAAGAAAADQAAABAAAAAAAAAABgAAAA4AAAAQAAAAAAAAAAcAAAAAAAAAEAAAAAAAAAAHAAAABgAAABAAAAAAAAAABwAAAAgAAAAQAAAAAAAAAAcAAAAKAAAAEAAAAAAAAAAHAAAACwAAABAAAAAAAAAABwAAAA0AAAAQAAAAAAAAAAcAAAAOAAAA --service-request-channel-token=14967363860962107892
kidistwinters      362   0.0  0.0  4332928   1248   ??  S     8Jan19   0:00.42 /System/Library/PrivateFrameworks/FamilyCircle.framework/Versions/A/Resources/familycircled
kidistwinters      353   0.0  0.1  4341780   3116   ??  S     8Jan19   0:06.78 /System/Library/PrivateFrameworks/CommerceKit.framework/Versions/A/Resources/commerce
kidistwinters      352   0.0  0.1  4892112   5168   ??  Ss    8Jan19   0:07.62 /System/Library/CoreServices/Dock.app/Contents/XPCServices/com.apple.dock.extra.xpc/Contents/MacOS/com.apple.dock.extra
kidistwinters      349   0.0  0.1  4333820   2944   ??  S     8Jan19   0:09.82 /System/Library/PrivateFrameworks/UserActivity.framework/Agents/useractivityd
kidistwinters      348   0.0  0.2  4355948   8188   ??  S     8Jan19   0:28.15 /usr/libexec/sharingd
kidistwinters      343   0.0  0.5  4924144  21640   ??  S     8Jan19   0:18.08 /System/Library/CoreServices/NotificationCenter.app/Contents/MacOS/NotificationCenter
kidistwinters      341   0.0  0.2  4345144   6652   ??  S     8Jan19   1:11.25 /usr/libexec/nsurlsessiond
kidistwinters      340   0.0  0.2  4921112   8224   ??  S     8Jan19   0:15.59 /System/Library/CoreServices/Spotlight.app/Contents/MacOS/Spotlight
kidistwinters      335   0.0  0.1  4335784   5100   ??  S     8Jan19   0:04.03 /usr/sbin/usernoted
kidistwinters      328   0.0  0.0  4306412   1632   ??  S     8Jan19   0:01.17 /usr/libexec/rapportd
kidistwinters      326   0.0  0.1  4341876   2952   ??  S     8Jan19   0:55.90 /System/Library/PrivateFrameworks/CloudDocsDaemon.framework/Versions/A/Support/bird
kidistwinters      324   0.0  0.0  4307468    924   ??  S     8Jan19   0:00.28 /Applications/Google Chrome.app/Contents/Versions/71.0.3578.98/Google Chrome Framework.framework/Helpers/crashpad_handler --monitor-self-annotation=ptype=crashpad-handler --database=/Users/kidistwinters/Library/Application Support/Google/Chrome/Crashpad --metrics-dir=/Users/kidistwinters/Library/Application Support/Google/Chrome --url=https://clients2.google.com/cr/report --annotation=channel= --annotation=plat=OS X --annotation=prod=Chrome_Mac --annotation=ver=71.0.3578.98 --handshake-fd=8
kidistwinters      320   0.0  0.1  4334324   4952   ??  S     8Jan19   0:03.56 /System/Library/PrivateFrameworks/IMCore.framework/imagent.app/Contents/MacOS/imagent
kidistwinters      315   0.0  0.0  4333300   2080   ??  S     8Jan19   0:08.05 /usr/libexec/pkd
kidistwinters      312   0.0  0.1  4334508   3288   ??  S     8Jan19   0:50.24 /System/Library/Frameworks/ApplicationServices.framework/Frameworks/ATS.framework/Support/fontd
kidistwinters      310   0.0  0.1  4344808   4804   ??  S     8Jan19   0:08.02 /System/Library/PrivateFrameworks/IDS.framework/identityservicesd.app/Contents/MacOS/identityservicesd
kidistwinters      303   0.0  0.0  4305832   1636   ??  S     8Jan19   0:01.54 /usr/libexec/pboard
kidistwinters      300   0.0  0.5  4992048  20592   ??  S     8Jan19   2:03.49 /System/Library/CoreServices/Finder.app/Contents/MacOS/Finder
kidistwinters      299   0.0  0.3  4900492  12876   ??  S     8Jan19   1:13.84 /System/Library/CoreServices/SystemUIServer.app/Contents/MacOS/SystemUIServer
kidistwinters      298   0.0  0.3  4923080  11376   ??  S     8Jan19   0:50.06 /System/Library/CoreServices/Dock.app/Contents/MacOS/Dock
kidistwinters      295   0.0  0.2  4912256   8804   ??  S     8Jan19   0:08.32 /Applications/Stickies.app/Contents/MacOS/Stickies -psn_0_61455
kidistwinters      293   0.0  1.2  6041152  51172   ??  S     8Jan19   5:28.81 /Users/kidistwinters/Desktop/Slack.app/Contents/MacOS/Slack -psn_0_53261
kidistwinters      291   0.0  0.0  4333188   2080   ??  S     8Jan19   0:02.49 /System/Library/CoreServices/sharedfilelistd
kidistwinters      288   0.0  0.0  4333080    188   ??  S     8Jan19   0:00.69 /System/Library/CoreServices/backgroundtaskmanagementagent
kidistwinters      283   0.0  0.1  4338968   4208   ??  S     8Jan19   0:04.40 /usr/libexec/lsd
kidistwinters      282   0.0  0.1  4346124   5152   ??  S     8Jan19   0:15.38 /System/Library/Frameworks/CoreTelephony.framework/Support/CommCenter -L
kidistwinters      280   0.0  0.1  4305860   2916   ??  S     8Jan19   0:08.98 /usr/sbin/distnoted agent
kidistwinters      278   0.0  0.1  4334628   5096   ??  S     8Jan19   0:17.98 /usr/libexec/UserEventAgent (Aqua)
kidistwinters      277   0.0  0.1  4306204   2476   ??  S     8Jan19   0:16.68 /usr/sbin/cfprefsd agent
kidistwinters      107   0.0  0.3  4901624  11916   ??  Ss    8Jan19   0:26.28 /System/Library/CoreServices/loginwindow.app/Contents/MacOS/loginwindow console
kidistwinters    16009   0.0  0.3  4315632  12736   ??  S     7:40PM   0:00.07 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    16007   0.0  0.5  4336172  20480   ??  S     7:40PM   0:00.39 /System/Library/PrivateFrameworks/SyncedDefaults.framework/Support/syncdefaultsd
kidistwinters    15948   0.0  0.4  4332428  15048   ??  S     7:31PM   0:00.19 /System/Library/PrivateFrameworks/AOSKit.framework/Versions/A/XPCServices/com.apple.iCloudHelper.xpc/Contents/MacOS/com.apple.iCloudHelper
kidistwinters    15941   0.0  0.2  4317184   9932   ??  S     7:30PM   0:00.12 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15939   0.0  0.2  4317184  10304   ??  S     7:30PM   0:00.12 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15924   0.0  0.6  4317472  23304   ??  S     7:25PM   0:00.29 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15597   0.0  0.5  4329932  22580   ??  S     7:18PM   0:00.43 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15590   0.0  0.6  4317184  24580   ??  S     7:18PM   0:00.12 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15586   0.0  0.6  4317184  23996   ??  S     7:18PM   0:00.14 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15585   0.0  0.4  4317948  17400   ??  S     7:18PM   0:00.17 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    15582   0.0  0.7  4317184  30432   ??  S     7:17PM   0:00.33 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    13605   0.0  0.7  4319484  27288   ??  S     6:44PM   0:00.29 /System/Library/Frameworks/CoreServices.framework/Frameworks/Metadata.framework/Versions/A/Support/mdworker_shared -s mdworker -c MDSImporterWorker -m com.apple.mdworker.shared
kidistwinters    13575   0.0  0.2  4334932  10204   ??  Ss    6:39PM   0:00.31 /System/Library/PrivateFrameworks/CloudDocsDaemon.framework/XPCServices/ContainerMetadataExtractor.xpc/Contents/MacOS/ContainerMetadataExtractor
...

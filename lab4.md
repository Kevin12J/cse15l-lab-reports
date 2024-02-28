# Lab Report 4: Vim
## Log into ieng6
![Step4](/Step4.png)
Type `ssh<space>kejacob@ieng6-201.ucsd.edu<enter>` in order to log into ieng6. I was not prompted to enter in my password because my ssh key was set up during a previous lab.
## Clone your fork of the repository from your Github account (using the SSH URL)
![Step5](/Step5Fix2.png)
Type `git<space>clone<space><command+v><enter>` in order to fork the repository from my Github account. I used `<command+v>` because I previously coppied the SSH URL from Github.
## Run the tests, demonstrating that they fail
![Step6](/Step6.png)
Type `cd<space>lab7<enter>` in order to go into the `lab7` directory. Then press `bash<space>test.sh<enter>` in order to run the script which runs the tests and shows that they fail.
## Edit the code file to fix the failing test
![Step7A](/Step7A.png)
![Step7B](/Step7B.png)
Type `vim<space>ListExamples.java<enter>` in order to edit the `ListExamples.java` file. Once inside the vim editor, press `G` in order to go to the end of the document and then press `kkkkkk` to go up to the line that needs to be changes. Press `E` to go to the end of the first word so the cursor will be over the `1` in `index1`. After that press `R` to enter replace mode and press `2` to change `index1` to `index2`. Finally, press `<esc>` to enter normal mode a press `:wq<enter>` in order to save and quit
## Run the tests, demonstrating that they now succeed
![Step8](/Step8.png)

Press `<up><up><enter>` in order to run the test script since the command was 2 up in the search history. The output shows that the tests ran successfully.
## Commit and push the resulting change to your Github account (you can pick any commit message!)
![Step9A](/Step9A.png)
![Step9B](/Step9B.png)

Type `git<space>add<space>.<enter>` in order to add the changes to the staging area and then create the commit by pressing `git<space>commit<enter>`. The vim editor will open in order to create the commit message. Press `i` to enter insert mode and type the commit message. After press `<esc>` to enter normal mode and press `:wq<enter>` to save and exit the commit message editor. Finally type `git<space>push<space>origin<space>main<enter>` in order to push the changes to the repository.

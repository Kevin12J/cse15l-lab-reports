# Lab Report 4: Vim
## Log into ieng6
![Step4](/Step4.png)
Type `ssh kejacob@ieng6-201.ucsd.edu` and then press `<enter>`. I was not prompted to enter in my password because my ssh key was set up previously.
## Clone your fork of the repository from your Github account (using the SSH URL)
![Step5](/Step5Fix.png)
Type `git clone https://github.com/Kevin12J/lab7.git` and then press `<enter>`. This is used to clone my fork of the repository using the SSH URL.
## Run the tests, demonstrating that they fail
![Step6](/Step6.png)
Type `cd lab7` and press `<enter>` in order to go into the `lab7` directory. Then type `bash test.sh` and press `<enter>` in order to run the script which runs the tests and shows that they fail.
## Edit the code file to fix the failing test
![Step7A](/Step7A.png)
![Step7B](/Step7B.png)
Type `vim ListExamples.java` and press `<enter>` in order to edit the `ListExamples.java` file. Once inside vim, press `<G>` in order to go to the end of the document and then press `<k><k><k><k><k><k>` to go up to the line that needs to be changes. Press `<E>` to go to the end of the first word so the cursor will be over the `1` in `index1`. After that press `<R>` to enter replace mode and press `<2>` to change `index1` to `index2`. Finally, press `<esc>` to enter normal mode a press `<:><w><q><enter>` in order to save and quit
## Run the tests, demonstrating that they now succeed
![Step8](/Step8.png)

Press `<up><up><enter>` in order to run the test script since the command was 2 up in the search history. The output shows that the tests ran successfully.
## Commit and push the resulting change to your Github account (you can pick any commit message!)
Press `<i>` to enter insert mode and type the commit message. After press `<esc>` to enter normal mode and press `<:><w><q><enter>` to save and exit the commit message.

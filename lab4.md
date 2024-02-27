# Lab Report 4: Vim
## Log into ieng6
![Step4](/Step4.png)
Press `<s><s><h><space><k><e><j><a><c><o><b><@><i><e><n><g><6><-><2><0><1><.><u><c><s><d><.><e><d><u><enter>` in order to log into ieng6. I was not prompted to enter in my password because my ssh key was set up during a previous lab.
## Clone your fork of the repository from your Github account (using the SSH URL)
![Step5](/Step5Fix2.png)
Press `<g><i><t><space><c><l><o><n><e><space><command+v><enter>` in order to fork the repository from my Github account. I used `<command+v>` because I previously coppied the SSH URL from Github.
## Run the tests, demonstrating that they fail
![Step6](/Step6.png)
Press `<c><d><space><l><a><b><7><enter>` in order to go into the `lab7` directory. Then press `<b><a><s><h><space><t><e><s><t><.><s><h><enter>` in order to run the script which runs the tests and shows that they fail.
## Edit the code file to fix the failing test
![Step7A](/Step7A.png)
![Step7B](/Step7B.png)
Press `<v><i><m><space><L><i><s><t><E><x><a><m><p><l><e><s><.><j><a><v><a><enter>` in order to edit the `ListExamples.java` file. Once inside the vim editor, press `<G>` in order to go to the end of the document and then press `<k><k><k><k><k><k>` to go up to the line that needs to be changes. Press `<E>` to go to the end of the first word so the cursor will be over the `1` in `index1`. After that press `<R>` to enter replace mode and press `<2>` to change `index1` to `index2`. Finally, press `<esc>` to enter normal mode a press `<:><w><q><enter>` in order to save and quit
## Run the tests, demonstrating that they now succeed
![Step8](/Step8.png)

Press `<up><up><enter>` in order to run the test script since the command was 2 up in the search history. The output shows that the tests ran successfully.
## Commit and push the resulting change to your Github account (you can pick any commit message!)
![Step9A](/Step9A.png)
![Step9B](/Step9B.png)

Press `<g><i><t><space><a><d><d><space><.><enter>` in order to add the changes to the staging area and then create the commit by pressing `<g><i><t><space><c><o><m><m><i><t><enter>`. The vim editor will open in order to create the commit message. Press `<i>` to enter insert mode and type the commit message. After press `<esc>` to enter normal mode and press `<:><w><q><enter>` to save and exit the commit message editor. Finally press `<g><i><t><space><p><u><s><h><space><o><r><i><g><i><n><space><m><a><i><n><enter>` in order to push the changes to the repository.

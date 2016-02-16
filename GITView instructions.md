## Starting from GitHub, and creating files
1) Create a repo on github.  If starting from scratch, do allow it to create a ReadMe. ![](img_0109.png)

2) Copy the repo address from the addressbar.  On IOS the little textbox with the clone address is tricky to select and copy, so just copy the address.   Now that it is in your clipboard, head back to Pythonista

3) Fire up `gitui` (from the action menu works best).  Click on the cline button.  The address will be prepopulated, and the local folder name will be guessed.  Edit if desired. **Add .git to the address**.  i.e. https://github.com/jsbain/repotest.git ![](img_0111.png)
Now you should see your files
![](img_0112.png)

4) Create some files in the new repo folder.  ![](img_0113.png)

5) Return to gitui tab (If you have run anything in the meantime... kill the tab and launch again.  I need to update gitui to survive global clearing.) Pull to refresh the file table.![](img_0114.png)

6) A few basic concepts about git are important to introduce here.  At any given time your file might exist in many places, perhaps different versions.  First is the working copy.  This is the folder you see in Pythonista, the files you directly edit,  Next is the index, or staging area.  Think of this as where you are building the next commit.  It too is just like a folder.  It starts out containing whatever was in the last commit.  You the `add` files to the index (staging area).   Once you are happy with what you have added, you `commit` files, which stores them in the repo.  
Now a commit is also just a folder, except that it stores a reference to what came before it, whomwrote it, the time, etc, all hashed with a `sha` so that each commit is unique and unchangeable.  The sha is the 20 digit number, often abbreviated to 6 or 7. The repo storage is basically just an unorganized set of commits, well, organized by sha only.
A branch is simply a pointer to a particular commit, that we give a name.  Since each commit stores its ancestor, once you have the starting point, you can walk backward to see history.  Literally, a branch pointer is just a file located at .git/refs/heads/branchname, containing nothing more than the 20 digit sha.  

7) Ok, so now we see our new file, press + in gitview to add the file.  The file moves from `untracked` to `staged:add`.  So a copy now exists in the index.  You can still modify the copy in pythonista, and press add again to update what is in staging area.  Once you are happy, you are ready to commit.

If you added a file which you did not want to add yet, the blue undo button lets you unstage a file.

8) To commit, type your name and email address in the commit line, along with a message describing why/what you changed.  Press commit.  The file now goes from staged to unmodified, meaning it is safely stored inside your repo.

9) Now, let's publish!  In gitview make sure the remote is selected (origin), and press push.  The first time you will be prompted for github username/pass, after it should be saved and you won't have to enter it again (stored in the keychain).  Success or failure is reported in the console. 

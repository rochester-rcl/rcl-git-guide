# Setup
1. Create a github account, and let Joe or Jeff know that you need to be added to the rcl-github organization. Provided you are in digital initiatives, let Channing know that you need to be added to the Digital Initiatives team.
2. Install [GitHub desktop](https://central.github.com/deployments/desktop/desktop/latest/win32?format=msi)
3. Open and Log into Github Desktop using your new GitHub credentials
4. Select File>Clone Repository
 
    ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/892278b1-1153-46ac-bf68-6e192585fce7)

5. Using the dialog that appears, select the repository you want to add. Note that you only need to clone a repository the very first time you work on a given project on a particular computer.
# Working on a Repository safely.
1. Immediately prior to any work, open github desktop, select the repository in question, and click "Fetch Origin". If you don't have the project in your "Current repository" dropdown, you will need to clone it first (see above).

    ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/6508f66b-77ac-441e-8290-b224a36cab89)
   
    This ensures that the copy of the project on your local computer is up to date with any changes that have been made by others.
2. Your github client should now look something like this: 

    ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/03bec171-5c9c-4a40-863e-55dbce5ab4b8)

   Click EITHER the button for "Open the repository in your external editor," or "view the files of your repository in explorer" at your choice. 
3. Make your changes locally using any software installed on your system, but do ***NOT*** move any files to outside the top level folder that GitHub desktop has created for the project on your system. Only changes within that folder will be tracked. 
4. When you are done making changes, review the changes made in GitHub desktop's interface. 

    ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/e4fdda78-e540-41e7-aa00-ede52e1a4692)

5. Once satisfied, write up a summary and description of your changes, and hit "Commit to master" (it may say commit to main, or some other word/ phrase after "commit to", that's fine)

    ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/6c339ac0-21cf-4e06-a298-93e70e7f8f33)

6. Finally, hit "push origin" once you have made all changes in your sitting.

    ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/8d93a118-201b-4993-a415-ed1100570807)

# Additional Notes
If you would like to add more points that can be rolled back to, make each point an individual commit. There is no need to push every time you commit. Just make sure that you DO push, as pushing is the act that actually updates the version of the project seen by others.
Be vigilant about Fetching, Committing, and Pushing frequently. Git gets much more complicated if you don't!
If you have questions, concerns, or strange behavior, please reference [this document](https://github.com/rochester-rcl/rcl-git-guide/tree/main) for a more in depth guide on Git, or ask Channing.
If you would like help on setting up change control for a new set of files, a new project, or new repository, please speak to Channing for assistance until you are familiar with the process.
Please look for places to use Git/Github wherever possible, as it allows for a much safer way of storing work history and allows for much greater collaboration.

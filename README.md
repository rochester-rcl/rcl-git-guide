# rcl-git-guide

# What is Git?
Git is a text version tracking system. That is to say it keeps track of changes to files, including a full history of all prior states of the file (when used properly), along with who made which changes when. While often associated with the website GitHub, it can be used indepentendly on your own computer, hosted on a local server, or used with a variety of websites other than GitHub. It can be used to keep track of files individually (for instance config files on a server), back up arbitrary text files to the cloud easily, and collaborate with others without overwriting work. Critically, Git only works properly with TEXT FILES, not BINARY FILES. You can determine the difference by opening a file in notepad. If it appears to have discernable structure, words, or anything that looks remotely human editable, it's a text based file. If, on the other hand, it looks like someone put a computer keyboard in a blender, and is full of characters that are not part of the english language, it's a binary file.

# Vocabulary
- **Repository**: A repository (or "repo") is where the files for a project live. Repositories can be organized into folders just like the filesystem on your computer, and can contain any filetype, though it is best practice for a number of reasons to only include certain varities and categories of files, expanded further upon in the "best practices" section of this document. If you're hosting git on a server or website like GitHub, the repository's master copy lives on the server. The repository is the point at which permissions are controlled for a project. For instance, someone may have the ability to read a repository, but not make changes to it, or to make changes to only certain sections of it.
 
- **Branch**: Repositories can be "branched" into different versions, like a tree. To take a practical example from our work, Drupal's latest version is version 10. The developers of Drupal, who are doubtless using Git, will have a branch to represent the most recent version of Drupal 10, but, since development work needs to also continue on 7 until the end of life date, there will be a seperate branch that split off from the main development branch at the release of drupal 8. A diagram of this is below.
![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/de3bebe6-4345-48bc-b407-d40e2e6870b4)

   In this diagram, the red line represents the series of changes to the drupal codebase that is considered the primary version of the codebase. This is itself a branch, called main (Note, other platforms or guides may use the terminology "Master." Due to the racial connotations, this terminology is no longer used in most cases, but the function is identical). Each line coming off is a point wherein the codebase was split into two identical copies, and allowed to diverge. In reality, a major project like drupal will have considerably more branches than this, but the simplification above will suffice for understanding. Much like "commit," "branch" can refer to either the act of creating a split, or the split itself.

- **Working Tree**: As seen above with "Branch," git often relies on tree analogies when explaining its operations. The series of commit operations on a repository is called the "Working tree." This includes commits on the current branch, as well as other branches. The diagram above would be an very primitive example of a working tree Diagram, which can be used to better understand the series of changes made to a repository.

- **Commit**: Git does not autosave your work. This makes sense considering both the fact that it tracks historical states of data, and in that its primary use is for the management of code; software under active development spends very little time in a fully functional state that is useful to share with other developers compared to, say, a word document. As such a manual save operation is performed. These saves are called "Commits," and are the basic unit of history within Git . At any point when working on a repository, you can commit your changes, and it creates a point that you can restore back to on your particular branch at any time (note that, depending on context, "commit" is used as both a noun to refer to the savepoint, and a verb to refer to the act of creating a savepoint). Notably, you do not save the whole project when you make a commit, you commit your changes to the branch you are working on since your last commit. This allows you to compare changes to the project on a file by file, line by line level.

- **Clone**: In the definitions above, we have largely ignored the fact that git can run locally OR on a server elsewhere. If you want to work on a repository that is stored on the web or on a git server from your local machine (as you will in most cases), you must first clone the repository. Cloning consists of copying a specific commit on a specific branch, most typically the latest commit of a given branch. This functionally creates a duplicate repository on your local system, with the chosen branch serving as the "Main" branch. You are then free to make edits and commits to your local working tree. These commits are not recorded on the remote server merely by cloning, recording local changes on the remote repository requires a "push" (explained further below).

- **Merge**: Changes made on one branch are sometimes beneficial to the development work of another. In this instance, a merge operation can be used to copy changes from one branch to another.
![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/185fae9e-e68f-4dd6-b11c-428dc42f3f94)

  If we look at this expanded tree diagram, we see a merge operation being performed, where changes on the "dev" branch are added to main, presumably after testing has been performed. Typically, you are merging younger branches onto older branches, but this is not always the case. When you merge a branch, the branch the changes are coming from does not cease to exist, though development work on that branch may cease if, for instance, the purpose of the branch was to prototype a new feature or release.

- **Diff**: Due to the nature of Git's change tracking, it is an extremely common occurrence to have multiple versions of the same file. Git therefore has a system for viewing the summary of differences between two versions called a "Diff". How Diffs are actually displayed varys from interface to interface, however there is some level of standardized convention. Generally speaking, the file will be displayed as two panes side by side with a linked scrollbar, with lines shared between the files ommitted entirely, lines removed shown with a minus sign preceeding, and/or highlighted in red, lines added shown with a plus sign preceeding, and/or highlighted in green, with a count of added and removed lines shown at the bottom. All lines will be numbered. Diffs can be used outside of git to compare files. [A more in-depth tutorial can be found here.](https://www.atlassian.com/git/tutorials/saving-changes/git-diff)

- **Push**: A "Push" is a special kind of commit where you take a commit or series of commits on your local working tree and move them to a version stored elsewhere, ususally the primary version of the repo stored on GitHub. Notably, if you've made multiple commits since your last push, Git does NOT collapse these commits down to a single point in time. Instead each commit is preserved and sent to the server individually, allowing you or another collaborator to go to say, the third commit out of 6 pushed at once. Should your commits conflict with other commits pushed to the repository since your last clone, it creates a "merge conflict" (detailed below), which must be resolved prior to pushing.

- **Merge Conflict**: When working in git, and performing a push or merge operation, it is entirely possible that other people have made commits to the same file, or perhaps even the same lines of the same files as your changes. When this happens, it is called a merge conflict. In this instance, you will be shown a Diff of the files, and given the option, block by block, to accept changes from one version to the other in order to resolve the conflict. Once this process is completed, you will be allowed to complete your operation.

- **Fork**: When the original development team wants to create a secondary version of the codebase, they typically use a branch. This is because branches are more tightly coupled to the original repository than their alternative, which is a fork. Forks are copies of the repository that have their own Main branch, their own branches .etc. This additional seperation is primarily useful when developers other than the original developers want to work on an open source project. It can also be used when one project gets split into two entirely seperate projects, such as the split between Omeka Classic and Omeka S.

- **Pull Request**: Branch is to Merge as Fork is to Pull Request... Sort of. When one wants to merge two branches together, or two forks together, and does not have permission to, they instead open a pull request. Pull requests have to be reviewed before the code change actually takes place. 

# What is GitHub?

Github is a major place where Git repositories are stored. The website serves as both a place where you can browse code and commit history, as well as a remote git server that stores your code in the cloud. Repositories on GitHub have a number of important features and configuration options, detailed below.

# What should these tools be used for?

Git should be used any time that text is being edited that is intended to be read by a computer. That is to say, scripts, programs, software, **config files**, etc. It is also a handy place to put documentation written in markdown (like this document) if there's a chance that the institution could benefit from storing a change history. By keeping that history in Git, it allows us to have more comprehensive versioning than something like box.

I emphasize server config files as a place where git can be utilized as it allows us, should we choose to going forward, to centrally manage config files for similar servers, and reduce manual effort.

Should files be in your repository directory that should NOT go into git, you can create a file called .gitignore and list those files there, git will, well, ignore them. This is handy for binary files, because, as mentioned, those don't play nice with Git, as well as editor config files, since presumably nobody wants to have anyone else's editor project settings.

# Repository Basics

Repositories in GitHub have several important values, detailed below:

- Owner
- Visibility
- Permissions

# Git Tools
# Basic Operations
- Merge 
- 
# Github features
# What is a Diff
# Intermediate Git Operations
# Understanding what's going on under the hood
# Best practices and standards
# Learning More

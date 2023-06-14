# rcl-git-guide

# What is Git?
Git is a text version tracking system. That is to say it keeps track of changes to files, including a full history of all prior states of the file (when used properly), along with who made which changes when. While often associated with the website GitHub, it can be used indepentendly on your own computer, hosted on a local server, or used with a variety of websites other than GitHub. It can be used to keep track of files individually (for instance config files on a server), back up arbitrary text files to the cloud easily, and collaborate with others without overwriting work. Critically, Git only works properly with TEXT FILES, not BINARY FILES. You can determine the difference by opening a file in notepad. If it appears to have discernable structure, words, or anything that looks remotely huuman editable, it's a text based file. If, on the other hand, it looks like someone put a computer keyboard in a blender, and is full of characters that are not part of the english language, it's a binary file.

# Vocabulary
- **Repository**: A repository (or "repo") is where the files for a project live. Repositories can be organized into folders just like the filesystem on your computer, and can contain any filetype, though it is best practice for a number of reasons to only include certain varities and categories of files, expanded further upon in the "best practices" section of this document. If you're hosting git on a server or website like github, the repository's master copy lives on the server. The repository is the point at which permissions are controlled for a project. For instance, someone may have the ability to read a repository, but not make changes to it, or to make changes to only certain sections of it.
- 
- **Branch**: Repositories can be "branched" into different versions, like a tree. To take a practical example from our work, Drupal's latest version is version 10. The developers of Drupal, who are doubtless using Git, will have a branch to represent the most recent version of Drupal 10, but, since development work needs to also continue on 7 until the end of life date, there will be a seperate branch that split off from the main development branch at the release of drupal 8. A diagram of this is below.
![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/de3bebe6-4345-48bc-b407-d40e2e6870b4)

   In this diagram, the red line represents the series of changes to the drupal codebase that is considered the primary version of the codebase. This is itself a branch, called main (Note, other platforms or guides may use the terminology "Master." Due to the racial connotations, this terminology is no longer used in most cases, but the function is identical). Each line coming off is a point wherein the codebase was split into two identical copies, and allowed to diverge. In reality, a major project like drupal will have considerably more branches than this, but the simplification above will suffice for understanding.

- **Commit**: Git does not autosave your work. This makes sense considering both the fact that it tracks historical states of data, and in that its primary use is for the management of code; software under active development spends very little time in a fully functional state that is useful to share with other developers compared to, say, a word document. As such a manual save operation is performed. These saves are called "Commits," and are the basic unit of history within Git . At any point when working on a repository, you can commit your changes, and it creates a point that you can restore back to on your particular branch at any time (note that, depending on context, "commit" is used as both a noun to refer to the savepoint, and a verb to refer to the act of creating a savepoint). Notably, you do not save the whole project when you make a commit, you commit your changes to the branch you are working on since your last commit. This allows you to compare changes to the project on a file by file, line by line level.

- **Clone**:

- **Push**:   



- **Merge**: Changes made on one branch are sometimes beneficial to the development work of another. In this instance, a merge operation can be used to copy
![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/185fae9e-e68f-4dd6-b11c-428dc42f3f94)


- **Fork**: When the original development team wants to create a secondary version of the codebase, they typically use a branch. This is because branches are more tightly coupled to the original repository than their alternative, which is a fork. Forks are copies of the repository that have their own Main branch, their own branches .etc. This additional seperation is primarily useful when developers other than the original developers want to work on an open source project. It can also be used when one project gets split into two entirely seperate projects, such as the split between Omeka Classic and Omeka S.



- **Pull Request**:



# What is GitHub?
Github is a major place where 
# What should these tools be used for?
# Repository Basics
# Basic Operations
- Merge 
- 
# Github features
# What is a Diff
# Intermediate Git Operations
# Understanding what's going on under the hood
# Best practices and standards
# Git Tools
# Learning More

# rcl-git-guide

# What is Git?
Git is a text version tracking system. That is to say it keeps track of changes to files, including a full history of all prior states of the file (when used properly), along with who made which changes when. While often associated with the website GitHub, it can be used indepentendly on your own computer, hosted on a local server, or used with a variety of websites other than GitHub. It can be used to keep track of files individually (for instance config files on a server), back up arbitrary text files to the cloud easily, and collaborate with others without overwriting work. Critically, Git only works properly with TEXT FILES, not BINARY FILES. You can determine the difference by opening a file in notepad. If it appears to have discernable structure, words, or anything that looks remotely huuman editable, it's a text based file. If, on the other hand, it looks like someone put a computer keyboard in a blender, and is full of characters that are not part of the english language, it's a binary file.

# Vocabulary
- Repository: A repository is where the files for a project live. Repositories can be organized into folders just like the filesystem on your computer, and can contain any filetype, though it is best practice for a number of reasons to only include certain varities and categories of files, expanded further upon in the "best practices" section of this document. If you're hosting git on a server or website like github, the repository's master copy lives on the server.
- Branch: Repositories can be "branched" into different versions, like a tree. To take a practical example from our work, Drupal's latest version is version 10. The developers of Drupal, who are doubtless using Git, will have a branch to represent the most recent version of Drupal 10, but, since development work needs to also continue on 7 until the end of life date, there will be a seperate branch that split off from the main development branch at the release of drupal 8. A diagram of this is below.

![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/de3bebe6-4345-48bc-b407-d40e2e6870b4)


In this diagram, the red line represents the series of changes to the drupal codebase that is considered the primary version of the codebase. This is itself a branch, called main (Note, other platforms or guides may use the terminology "Master." Due to the racial connotations, this terminology is no longer used in most cases, but the function is identical). Each line coming off is a point wherein the codebase was split into two identical copies, and allowed to diverge. In reality, a major project like drupal will have considerably more branches than this, but the simplification above will suffice for understanding.
- Fork: When the original development team wants to create a secondary version of the codebase, they typically use a branch. This is because branches are more tightly coupled to the original repository than

# What is GitHub?
Github is a major place where 
# What should these tools be used for?
# Repository Basics
# Basic Operations
- Merge 
- ![image](https://github.com/rochester-rcl/rcl-git-guide/assets/24469058/185fae9e-e68f-4dd6-b11c-428dc42f3f94)

# Github features
# What is a Diff
# Intermediate Git Operations
# Understanding what's going on under the hood
# Best practices and standards
# Git Tools
# Learning More

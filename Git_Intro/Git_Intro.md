# Introduction to Git with Github.com

## Introduction

`git` is a software tool that allows authors to track file changes inside of a folder on a computer.  This special folder is called a _git repository_.  A _git repository_ is just a folder on a computer (_any computer_ locally or online) **PLUS** a small amount of meta-data stored in a hidden `.git/` folder in that same folder.

```
MyProject/
├── .git
│   └── // magic lives here ...
├── README.txt
└── src
    ├── MyClass.cpp
    └── MyClass.h
```

The `.git/` folder contains a history of file changes and configuration information that updated and accessed by the `git` software tool.  Users should avoid manually modifying the contents of the `.git/` folder (it's hidden for your protection!).

When the original author decides to share a _git repository_ folder with another user, the new user can freely change the folder's contents.  The user might update a chapter in a novel, improve existing source code or add documentation in a new subdirectory.  The user can then use various `git` software tool commands to save those changes into the `.git/` folder of the repository. 

`git` is then able to intelligently `merge` the original author's folder with the collaborator's modified folder, resulting in an updated folder that everyone can continue working on together.    

[github.com](http://github.com) is a place online to keep copies of repositories.  You can create repositories or contribute to the repositories of others.  

## Terms

- The _repository_ (see above).
- The _index_ is a list of _tracked_ files and folders in a _repository_.  `git` is _aware_ of.  Any file can be added to the _index_.  Folders are not added unless there is a file in them.  Select files and folders can be excluded using strategically constructed `.gitignore` files.

- `add` Add files to the current _index_ of tracked files and their changes.  An _index_ is a list of the files and folders currently being tracked for changes by `git`. 

- `commit` -


... to be continued



# Other Resouces
- http://lifehacker.com/5983680/how-the-heck-do-i-use-github
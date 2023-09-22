# Git Essentials

Git is a version control system which helps you keep track of changes in your software project.

## Prerequisites
In order to practice the following concepts you'll need Git setup on your computer.
Learn how to setup at [Setup.md](Setup.md).

## Initializing a Git repository
Navigate to your project folder in terminal & use the following command to initialize a Git repository in your project folder.
```bash
git init
```
Now Git will keep a look on your folder.
> You can also notice that it has created a hidden folder called .git by executing ```ls -a```

> Confused by linux commands? Have a look at our [Command Line guide]()
## Adding files to Staging area
Now that Git has an eye over our project folder, it still won't keep track of the files in it by default & we need to tell it explicitly to track files.

Execute ```git status``` & it will show untracked files.

Now, execute 
```bash
git add .
```

This will add all the untracked files to a so called *"staging area"*. A fancy way of saying that now git will track changes in these files.

> As new files are created, they won't be in the staging area automatically & you'll have to add them to staging area by yourself.  
Once a file has been added to staging area you don't need to add it again.

## Creating commits
Now that git is tracking changes in your files, you'd want to create **snapshots** of your project so that you can get back to that state in the future.
In git terminology, these are known as *commits*.

Create a commit by executing
```bash
git commit -m "My Message"
```
Where *My Message* can be anything you wish, these are labels that you can later use to identify commits as human beings.

After making changes later to your files, save them & make more commits whenever you feel the need to.

> You can view the history of previous commits by executing ```git log```.  
Got stuck scrolling endlessly in the history? Press the ```q``` key to exit the history view.

## Pushing repository to GitHub
Right now, your repository exists on your computer. If you need to share it with your friends or team, you need some other place to store your repository. Here [GitHub.com](https://github.com) comes into the picture. GitHub is a remote repository hosting service where developers store & manage their code.

Log in to your account on [GitHub.com](https://github.com) & click on the create repository button. \
Give your repository a name of your choice and hit *Create*.

> TODO: Add screenshot of create button

Now copy the appropriate URL (HTTPS/SSH) of your repository depending upon your setup.

> TODO: Add URL screenshot

Now, to link the local repository on your computer to the newly created GitHub repository, execute the following

```bash
git remote add origin <UrlYouCopied>
```
Where ```<UrlYouCopied>``` is the url you copied from GitHub.

Now, your local repository is linked to your repository on GitHub, to upload your code to GitHub, execute the following

```bash
git push -u origin master
```
Here ```master``` is your branch name.

The ```-u``` "flag" is used in case the branch does not already exist in the remote repository. When you push later changes the ```-u``` flag isn't necessary.

> In case your branch name is ```main``` instead, change the above command to use main instead of master.
Know your current branch name through use of ```git status```

> For pushing changes to GitHub, your repository must not have any uncommited changes. So make sure you commit your changes before pushing them.

## Working with branches
Now, Imagine you're working on a big project with your team, and you want to keep track of different parts of the project without messing things up. Git branches are like separate paths or copies of your project where you can make changes and try out new things without affecting the main project.

Git creates the main branch by default. This is the "official" version of your project. It's like the main road everyone follows. It should always be stable and ready to use.

When you want to add a new feature or fix a bug, you create a separate branch. It's like taking a detour from the main road to work on something specific. This way, your changes won't affect the main project until you're ready.

> TODO: Add branching img

### Creating a new branch
Create a new branch by executing
```bash
git branch <BRANCHNAME>
```
Where ```<BRANCHNAME>``` is your chosen name for your branch.

Now you've created a new branch but you're still working in your main branch. To switch to your newly created branch, execute the following

```bash
git checkout <BRANCHNAME>
```
Now, whatever commits you make will be saved into this new branch. \
You can switch again to the main branch by executing ```git checkout main```

> A shortcut is ```git checkout -b <BRANCHNAME>``` which creates a new branch with the name provided & also switches to it.

### Merging branches
Once you've finalised your feature & want your changes to be reflected in the main branch, you "merge" your branches. It's like rejoining the main road, but now it has your improvements.

Now, switch to the main branch with ```git checkout main``` & execute the following to merge your changes from ```<BRANCHNAME>``` to your ```main``` branch.

```bash
git merge <BRANCHNAME>
```

> While merging, Git tries to incorporate all the changes in your files but sometimes it couldn't determine which of the lines to choose among the two branches. This leads to something called "merge conflicts", resolving merge conflicts is beyond the current scope of this document but you can learn more about it [here](https://docs.github.com/en/pull-requests/collaborating-with-pull-requests/addressing-merge-conflicts/about-merge-conflicts).

### Pushing your branches to GitHub
If you want to push your branch to GitHub as well, switch to your branch & execute the following to create your branch in the remote repository & push your changes as well.
```bash
git push -u origin <BRANCHNAME>
```
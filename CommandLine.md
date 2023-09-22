# Command Line Essentials
Learn the basic commands to use your computer via command line by this document.

Command line is a way to interact with your computer using text commands instead of graphical interfaces (like clicking icons with a mouse). 

Using command line can seem intimidating at first, but it's a valuable skill that can make your interaction with computers more efficient and powerful.

## Prerequisites
For following the examples in this document, open "Git Bash" in Windows (Installed by default with Git). Or open "Terminal" if on MacOS or Linux.

## Understanding the prompt
When you open the command line, you'll see a window with some text. This is your command prompt. It often displays your username, computer name, and the current directory (folder) you're in. It looks similar to this.

On Windows (Git Bash):

> TODO: Add Git Bash Screenshot

On Mac/Linux:

> TODO: Add Terminal Screenshot

## Navigation
Here are some common commands to navigate around the filesystem.

```cd <PATH>``` - Changes the current working directory to given ```<PATH>```.

> eg. ```cd Downloads``` or ```cd Documents/MyFolder```

When ```<PATH>``` isn't provided, cd navigates to the home directory of your computer.

```ls``` - Shows files in the current working directory

```ls -l``` - Same as ```ls``` but shows in list view

```ls -a``` - Same as ```ls``` but also shows hidden files

```ls -al``` - Combination of the above two

> Here, ```-a``` & ```-l``` are known as the flags for the command

```mkdir <FOLDERNAME>``` - Creates a new folder with the given name in the current working directory.

> eg. ```mkdir Projects```

```touch <FILENAME>``` - Creates an empty file with the given name in the current working directory.

> eg. ```touch myfile.txt``` or ```touch app.py```

```rm <FILENAME>``` - Deletes the file with the given name from the current working directory.

> eg. ```rm app.py```

```rm -r```

```rmdir```

```clear```
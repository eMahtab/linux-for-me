# linux-for-me
Linux Cheatsheet

1. Creating a new directory in linux
   ```
   mkdir work
   
   ```
   Above command will give error if work directory already exist. If we use the p option with mkdir it will not give error      even if the directory already exist
   ```
   mkdir -p work
   
   ```

2. Creating a new file or editing an existing file (using gedit editor)
   ```
   gedit index.html
   ```

3. Copying a file (index.html) from one directory (e.g. /home/bourne/work) to another (e.g. /home/bourne/Downloads)
   ```
   
   cp /home/bourne/work/index.html /home/bourne/Downloads
   
   ```

4. Changing the current directory to home directory (e.g. /home/bourne or /home/mahtab)
   ```
   cd ~
   ```

5. Changing current directories using ~ symbol
   ```
   cd ~/work
   cd ~/Downloads
   ```
   
6. Copying a directory (/home/bourne/work) to another directory (/home/bourne/Videos)
   ```
   cp -R /home/bourne/work /home/bourne/Videos/
   or
   cp -r /home/bourne/work /home/bourne/Videos/
   ```
   
7. Removing a file (e.g. /home/bourne/Videos/work/info.txt)
   ```
   rm /home/bourne/Videos/work/info.txt
   ```
8. Removing a directory ( e.g. /home/bourne/Videos/work ) **recursively**

   ```
   rm -r ~/Videos/work
   ```
9. Removing all the files in a directory (e.g. ~/codes/) 
  ```
  rm ~/codes/*
  ```
  
  **Note that above command will only delete all the files under codes directory but it won't delete any sub-directories under codes**

10. Deleting files and sub-directories under a directory (e.g. /home/bourne/codes)
     ```
     rm -r ~/codes/*
     ```
11. Renaming a file (e.g. ~/codes/alpha.txt to ~/codes/awesome.txt)

    ```
    mv ~/codes/alpha.txt ~/codes/awesome.txt
    ```
12. Renaming a folder (e.g. ~/codes to ~/sourceCodes)
    
    ```
    mv ~/codes ~/sourceCodes
    ```
13. Counting the number of files in a directory 
    
    ```
    ls -l | wc -l
    ```
    **Note that above command will give the result one greater than the actual number of files**
    
14. Clearing the terminal screen
 
     ```
     clear
     ```

   # Vi Editor Cheatsheet
 
    **Opening a file in vi editor**
    
    ```
    vi nameOfTheFile
    ```
    **Closing an open file and Quiting the vi editor**
    
    ```
    :q
    ```
    **Saving and closing a file and quitting the editor**
    
    ```
    :wq
    ```
    
    **Switching from command mode to insert modes**
    ```
    To switch from command mode to insert mode use 'i'. To switch from insert mode to command mode use 'esc' key
    ```
    
    **Editing a file**
    ```
    To edit a file in vi ceditor first switch to insertion mode ( by pressing esc and then i), once you are in insertion mode
    you can edit the file
    ```
    
    **Deleting characters**
    ```
    To delete a single character use 'x' in command mode and to delete a complete line use 'dd' in command mode  
    ```
    
    **Moving in lines up and down, right and left**
    ```
    To move between lines up and down use arrow keys in command mode. To move left and right use left and right arror keys in command mode 
    ```

   # Grep Command
  
  **Searching for a string in a file**
  
   ```
   grep CGHR someText.txt
   ```
  **Case Insensitive Search with Grep**
   
   ```
   grep -i cghr someText.txt
   ```
   
  **Printing the line numbers in the output result**
  
   ```
   grep -ni cghr someText.txt
   ```
   
  **Seraching for a string with multiple words**
  
  ```
  grep -ni "quote is must" grep101/someText.txt
  ```
  
  **Searching in multiple files**
  ```
  grep -in grunt grep101/someText.txt grep101/otherText.txt
  ```
  
  **Searching for a pattern recursively in all the files under a directory**
  
  ```
  grep -inr grunt grep101
  ```
  
  **Coloring the matched string**
  
  ```
  grep -r --color mahtab .
  ```
  
  **Git grep**
  
  If you are working with a gir repository then git grep ignores all the files and directories defined in .gitignore file
  ```
  git grep mahtab .
  ```
  
  **Getting context around grep matches**
  
  A = after, B = before, C = both after and before
  ```
  grep --color -rn -C 2 mahtab .
  ```
  
  **Using special characters . and * with grep**
  
  . means any character and * means zero or more occurances
  ```
  grep --color -rn "(http.*)" .
  ```
  
  **grep escaping the special characters**
  
  If you want special characters to be treated as normal characters you can escape it with \
  ```
  grep -nr "www\." . .
  ```
  
  **grep extended reguluar expressions**
  
  by default grep treats . and * as special characters, grep also supports extended regular expressions 
  +(one or more) and ?(zero or one) symbols. To use it either you can use the -E option with grep or escape these             characters with backslash(\) to be treated as special characters
  ```
  grep -nr -E "https?" .
  
  or
  
  grep -nr "https\?" .
  ```
 
 # Find command
 
 find command is used for searching for files 
 
 **Searching for specific file**
 
 ```
 find -name cme-esb.xml
 ```
 By default find will look for file under current directory and sub-directories
 
 **Searching all ejs files inside views directory**
 
 ```
 find views -name "*ejs"
 ```
 
 **Combining find and grep together with xargs**
 
 ```
 find views/ -name "*ejs" | xargs grep -in "bangalore"
 ```
 
 
 
 
 
 **Shortcut for opening a terminal**
 
 If you are on a Ubuntu machine you can open a new terminal by pressing the keys Ctrl+Alt+t but this shortcut does not work in Debian so you have to set this shortcut manually to open the terminal using Ctrl+Alt+t
 
 **To find out what version of Linux (distro) you are running**
 
 You can use the below command to find out which version of linux you are running
 ```
 cat /etc/*-release
 ```
 # scp (secure copy) 
 To copy a directory from your local machine to remote server's /var/www/html/ directory
 
 ```
 scp -r mansa2 mahtab@net.mahtabalam:/var/www/html/
 ```
 To copy a file from remote server to your local machine
 ```
 scp mahtab@net.mahtabalam:/var/www/data/abc.wav /home/mahtab/recordings/
 ```
 #chown (changing ownership)
 To change owner and group owner to root for all the files and sub directoies within a directory use below command
 ```
 sudo chown -R root:root mansa2
 ```
 #chmod (changing permissions)
 To change permissions for a folder
 ```
 sudo chmod 755 mansa2
 ```
 To change permission for all the files under a directory 
 ```
 sudo chmod 644 mansa2/*
 ```
 Note that above command will not change file permissions for sub directories and files inside sub directories
 
 # Zipping a directory
  ```
   zip -r name-of-the-zip-to-be-created.zip dir
  ```
  
 # Zipping a single file
 ```
   zip name-of-the-zip-to-be-created.zip file
 ```
   
# Using tar to compress a dir into a .tgz file

```
 tar -czf compressed-file-name.tgz dir
```
# Using tar to list files inside .tgz file

```
 tar -tzf compressed-file-name.tgz
```
# Using tar to uncompress a .tgz file
 ```
 tar -xzf compressed-file-name.tgz
 ```

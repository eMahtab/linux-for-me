# linux-for-me
Linux Cheatsheet

1. Creating a new directory in linux
   ```
   mkdir work
   
   ```

2. Creating a new file/ editing an existing file (using gedit editor)
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
    To move between lines up and down use arrow keys in command mode. To move left and right use left and right arror keys in command     mode 
    ```


Commands 

1. ***Create a group***
      
      ```
      $ sudo addgroup <groupname>
      ```
      
      Add an existing user into this group
       
      ```
      $ sudo adduser <username> <groupname>
      ```
  
2. ***Change a group of the folder***

      ```
      $ sudo chgrp <groupname> <path_of_folder>
      ```
      
      example:
      
      ```
      $ sudo chgrp other_accounts /mnt/cv
      ```  

3. ***Create a link***
      ```
        $ ln -s  <real folder> <linked path>
      ```  
      example:
      ```
        $ ln -s /mnt/cv  ~/.
      ```
      This will create a link of /mnt/cv folder at home directory with name cv
  
4. ***Change the name of user login***

      Three steps are followed as follows:
      Before starting just see the following information of your current login by
      ```
      $ id <login-name>
      ```
      Sample Output of ```$ id rohit```
      
      ```uid=602(rohit) gid=602(rohit) groups=602(rohit),29(sudo)```
      
      It shows the id of the user as well as group id to which the user belongs.
            
      **Step-1:** *Change the name of login:*
      ```
      $ sudo usermod -l <new-login-name> <old-login-name>
      ```
      It will change the old-login-name with new-login-name. But it will not change the group of the id.
            
      **Step-2:** *If you want to change the group of your id to your new-login-name:*  
      ```
      $ sudo groupmod -n <new-login-name> <current-group-name>
      ```
      This will change the groupname of the with new group name.
      verify it using  ``` $ id <login-name> ```
            
      **Step-3:** *Change the name of home folder by new-login-name:*
      ```
      mv /home/<old-login-name> /home/<new-login-name>
      ```
      
      **Step-4:** *Mention the updated path in the /etc/passwd:*
      
      Open the file ``` $ sudo nano /etc/passwd ```
      
      Output will be like 
      ```
      <new-login-name>:x:602:602:<new-login-name>,,,:/home/<old-login-name>:/bin/bash
      ```
      
      Here, change the path ```/home/<old-login-name>``` to ```/home/<new-login-name>``` then Ctrl+o and Ctrl+x to save the file.
      Now logout of the system and login.  To verify type ```$ pwd ``` and output should be ```/home/<new-login-name>```
      
      Done!!

5. ***Lock the user account***

      Command syntax is as ```chage -E 0 {username}```. For example:
       
      ```
      sudo chage -E 0 vivek  
      ```
      
6. ***UnLock the user account***

      Command syntax is as ```chage -E -1 {username}```. For example:
       
      ```
      sudo chage -E -1 vivek  
      ```      

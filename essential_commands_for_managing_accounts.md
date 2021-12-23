
Commands 

1. ***Create a group***
       
       `$ sudo addgroup <groupname>`
       
        Add an existing user into this group
        ```
        $ sudo adduser <username> <groupname>
        ```
  
2. ***Change a group of the folder***

        chgrp command:

        syntax:  

        $ sudo chgrp <groupname> <path_of_folder>
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
  

  

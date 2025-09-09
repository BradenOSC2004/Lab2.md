## Lab 02

- Name: Braden Henry
- Email: Henry.284@wright.edu

Instructions for this lab: https://pattonsgirl.github.io/CEG2350/Labs/Lab02/Instructions.html

## Part 1 Answers

Full / absolute path to your private key file: 

Command to SSH to AWS instance:
```
[ssh -i ceg2350.pem ubuntu@18.214.172.33]
```

## Part 2 Answers

1. `chmod u+r bubbles.txt`
    - Means: gives the user permissions to read the bubbles file
    - Assessment: changing permissions to who and who cant read a file on your system is generally a good thing, but doesnt change anything for anyone else just the user.  
2. `chmod u=rw,g-w,o-x banana.cabana`
    - Means: This gave the user permissions to read and write but removed permissions for groups write to the file and for owners to execute the file
    - Assessment: With a command like this focuses on more than just the user but does allow other people to mess with the file which everyone may not want. 
3. `chmod a=w snow.md`
    - Means: this means that every user can now write to this file
    - Assessment: This command is another bad one. There is no permission given so that the owner can do anything with the file besides write to it. 
4. `chmod 751 program`
    - Means: This command gives the owner access to everything, the group can only read and write to the file, and everyone else can only execute it
    - Assessment: This command is better because it aleast gives the owner full control over the file
5. `chmod -R ug+w share`
    - Means: This command adds write permissions to the file for all files and subdirectories because it was made recursive with -R
    - Assessment: This command is also good because it allows the owner and said groups to work on the same file

## Part 3 Answers

1. Command to create new user: sudo adduser
2. Path to new user's home directory: /home/ubuntu
3. Evaluate if `ubuntu` can add files to new user's home directory: Yes they can
4. Command to switch to new user: sudo su
5. Command(s) to go to new user's home directory: cd
6. Evaluate if new user can add files to user's home directory: putting the permissions to 770, let me add some files
7. Command to return to `ubuntu` user: sudo su ubuntu
8. Command to return to `ubuntu` home directory: cd

## Part 4 Answers

1. Command(s) to create group named `squad` and add members: sudo groupadd squad
2. Command(s) to add `ubuntu` & user to group `squad`: sudo usermod -G ubuntu, sudo usermod -G bhenry
3. Command(s) to allow `squad` to view the `ubuntu` user's home directory contents: sudo chmod 750 /home/ubuntu, sudo chgrp squad /home/ubuntu
4. Command(s) to modify `share` to have group ownership of `squad`: sudo chgrg -R squad share
5. Describe your tests and commands with the user account: Because of the group squad, I can now look at the home directory, when before I was denied. Additionally, because of permissions given to the group, I can now add a file to it. 
6. Describe the full set of permissions / settings that enable the user to make edits: As the user Bhenry, when creating a file in the share folder, I added permission 770 which meant the user and the group could read, write, and execute files. Like before the permissions given in the group as well allows bhenry to make edits or add things.  

## Part 5 Answers

For each, write the command used or answer the question posed.

1. Command(s) to make file using `sudo`: 
2. Command(s) to make file with `root`:
3. Describe / compare ownership and permissions of files:
4. Which account can do what actions? (Type Y or N in columns)

Contents inside of `share`
| Account   | Can View  | Can Edit  | Can Change Permissions    |
| ---       | ---       | ---       | ---                       |
| `root`    |           |           |                           |
| `ubuntu`  |           |           |                           |
| `BOB`     |           |           |                           |

`madewithsudo.txt`
| Account   | Can View  | Can Edit  | Can Change Permissions    |
| ---       | ---       | ---       | ---                       |
| `root`    |           |           |                           |
| `ubuntu`  |           |           |                           |
| `BOB`     |           |           |                           |

5. Command(s) to modify permissions:
6. How to give user account `sudo`:

## Citations

https://linuxize.com/post/how-to-add-user-to-group-in-linux/
https://www.redhat.com/en/blog/linux-user-group-management


 

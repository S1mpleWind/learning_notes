# Shell

shell is a very powerful tool , eg bash .  
here are some notes that might be helpful .

## Special variables

bash use special variables to refer to arguments , like :

- `$0` : name of the script
- `$1-9`: arguments to the script 
- `$@` : all the arguments
- `$#` : number of arguments
- `$?` : return code of the previous command
- `$$` : PID
- `!!` : whole last command
- `$_` : last argument from last command

## Important Commands

- `ls` : use ls to check the files under the current directory
- `mkdir` : create a directory
- `cp` : copy a file
- `mv` : move a file , or use it to *rename* file
- `help` : when unclear about a command , just type `--help` to see for helping document
# Shellscripting

Shell scripting helps to automate repetative tasks.
Bash scripting are series of commands and instructions that are sequentially excuted in a shell. These commands are created in shell by saving a collection of commands in a textfile with `.sh` extentios and executed from the command line or called from other scripts.

Shell scripts allows the user to define and work with variables ( numbers, strings and arrays). Valus can be assigned to variables using the `=` operator and accessed using the variable name preceded by `$` sign

01 - First Shell Script

The image below shows how to make a directory and create file with `.sh` extention

![Alt text](img/01.step1-3png.png)

Note in the image below
The script must start with `#!/bin/bash`. 
`echo` command displays the text and `name` is the variable which the value entered by the user will be stored in.

![Alt text](img/02.nano.png)

The `sudo chomod +x user-file.sh` command changes the permission of the file, in this case user-input.sh, granting the execute permission to the owner. The `./` command specifies the path to the file to be executed 

![Alt text](img/03.hello.png)

The above results shows the script works as expected.



02 - Directory Manipulation and Navigation



![Alt text](img/21.openfilesystem.png)

The script below will create a new driectory called `my_diectory` and change to the directory. it will also create two files inside the directory, move one level back up and remove the `my_directory and its content and list the files in the current directory.

![Alt text](img/22.nanofilesystemcode.png)

Below is the result obtained showing that the above script works
![Alt text](img/23.result.png)

03 - File Operation and Sorting

 The aim here is to create some files, sort them alphabetically by name, display the sorted list, remove the original files, rename the sorted list file, and finally display the renamed file. In order to achieve this we have to create a shell script.

![Alt text](img/31.create.png)


Here is what the shell script will do step by step 

Create Files:

It creates three files named file1.txt, file2.txt, and file3.txt, each containing a simple text message.
Display Current Files Order:

It displays the files in the current directory using the ls command.
Sort Files Alphabetically:

It sorts the file names alphabetically using the ls command piped into the sort command and redirects the sorted output to a file named sorted_files.txt.
Display Sorted Files:

It displays the content of the sorted_files.txt file, which contains the sorted list of file names.
Remove Original Files:

It removes the original files file1.txt, file2.txt, and file3.txt using the rm command.

Rename Sorted File:

It renames the sorted_files.txt file to sorted_files_sorted_alphabetically.txt using the mv command.

Display Final Sorted File:

It displays the content of the renamed file sorted_files_sorted_alphabetically.txt.


![Alt text](img/32.nanacodesorting.png)

The result of the above script is shown in the image below

![Alt text](img/33.result.png)

04 - Working with Numbers and Calculations

Here we want to write a script that is able to use numbers and mathematical operators. 

![Alt text](img/41.create.png)


Here is the step by step explanation of what the script below will do

Shebang (#!/bin/bash):

This line specifies that the script should be interpreted by the Bash shell.

Variable Definition:

num1=10 and num2=5: These lines define two variables num1 and num2 with numeric values 10 and 5 respectively.

Basic Arithmetic Operations:
sum=$((num1 + num2)): Adds num1 and num2.
difference=$((num1 - num2)): Subtracts num2 from num1.
product=$((num1 * num2)): Multiplies num1 by num2.
quotient=$((num1 / num2)): Divides num1 by num2.
remainder=$((num1 % num2)): Computes the remainder of dividing num1 by num2.

Display Results:
echo "Number 1: $num1" and similar lines: These commands display the values of variables num1, num2, sum, difference, product, quotient, and remainder.

More Complex Calculations:
power_of_2=$((num1 ** 2)): Raises num1 to the power of 2.
square_root=$(echo "sqrt($num2)" | bc): Calculates the square root of num2 using bc, which is a command-line calculator.

Display Results:
echo "Number 1 raised to the power of 2: $power_of_2" and 
similar lines: These commands display the results of the more complex calculations.
![Alt text](img/42.nanocode.png)


This script above demonstrates basic arithmetic operations, variable usage, and more complex calculations using Bash shell scripting. It's a good example to understand how to perform mathematical operations and utilize external tools like bc within a Bash script

![Alt text](img/43.results.png)


05 - File Backup and Timestamp

This looks into backing up of databases and other storage devices. 

![Alt text](img/51.create.png)

Here is what the scripts will do

Shebang (#!/bin/bash):

This line specifies that the script should be interpreted by the Bash shell.

Variable Definition:

source_dir="/path/to/source_directory": This line defines a variable source_dir containing the path to the source directory.
backup_dir="/path/to/backup_directory": This line defines a variable backup_dir containing the path to the backup directory.

Create a Timestamp:

timestamp=$(date +"%Y%m%d%H%M%S"): This line uses the date command to generate a timestamp in the format "YearMonthDayHourMinuteSecond" and assigns it to the variable timestamp.

Create Backup Directory with Timestamp:

backup_dir_with_timestamp="$backup_dir/backup_$timestamp": This line constructs a new directory path by appending the timestamp to the backup directory path.

Create Backup Directory:

mkdir -p "$backup_dir_with_timestamp": This line creates the backup directory along with any necessary parent directories (-p option ensures that the command does not fail if the directory already exists).

Copy Files from Source Directory to Backup Directory:

cp -r "$source_dir"/* "$backup_dir_with_timestamp": This line copies all files and directories from the source directory to the backup directory. The -r option ensures that the copy is recursive (i.e., it copies directories and their contents). The /* ensures that only the contents of the source directory are copied, not the directory itself.

Display Backup Completion Message:

echo "Backup completed. Files copied to: $backup_dir_with_timestamp": This line prints a message indicating that the backup process is complete, along with the path to the backup directory.

![Alt text](img/52.nanocode.png)

In summary, the above script automates the process of creating a backup by copying all files from a specified source directory to a backup directory. It utilizes variables to store directory paths and a timestamp to create a unique backup directory. Finally, it provides feedback to the user by displaying a message upon completion.

![Alt text](img/53.result.png)


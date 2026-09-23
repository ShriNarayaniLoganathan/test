# Linux and Shell Programming Lab Manual

> GitHub-friendly Markdown conversion of the uploaded Linux Shell Programming Lab manuals.

**Programs covered:** 1–15

LINUX AND SHELL PROGRAMMING LAB
MANUAL FOR PROGRAMS

## PROGRAM 1

Basic Linux commands: rm, cp, cat, mv, cmp, wc, split, diff.

### PROCEDURE:

- STEP 1: Start the process
- STEP 2: In the normal command prompt of Linux perform the operations for following commands.
- STEP 3: Use Vi editor for creating files Vi Filename and use mkdir for creating directories mkdir directoryname.
- STEP 4: Use cat command to create,append and display the file on the screen cat >filename -to create cat >>filename -to append cat filename to display.
- STEP 5: Use wc command to count the lines,character and bytes in the respective file like wc filename.
- STEP 6: Use cp command to copy the old file into new file cp filename (old) filename 2 (new).
- STEP 7: Use cmp command to compare rm command to remove mv command to move and wc command to count the word from the file.
- STEP 8 : Finally use split command to split the one phase into another and diff command is to show the difference between one file with another.
- STEP 9: Type all this command in shell script file by creating vi filename.sh and execute it like by sh filename.sh.
- STEP 10 : Stop the process.

### SHELL SCRIPTS:

```bash
ls // To list all the files in the directory
cp file1 file2 // To copy a file
cat file2 // To View the Contents in file2
mv file3 file4 // To move files
cat file4 // Contents in file4
wc file1 // To see the word count
wc -l file1 // To see the line count
wc -w file1 // To see the words count
wc -c file1 // To see the character count
split -3 file1 // To split a file
head -3 file1 // To read a Initial lines of file
tail -3 file1 // To read a Last lines of file
cmp file1 file2 // To compare two files
diff file1 file2 // To differ two files
rm file6 // To remove a file6 from the directory
rm -r * // To remove all files from the directory
```

## PROGRAM 2

Write a shell script to implement the user and System information by commands.

### PROCEDURE :

- STEP 1: start the process.
- STEP 2: In the shell prompt window perform the following commands use logname to check log name of user, shell to check the following shell information.
- STEP 3: type ostype command to check the ostype of Linux os.
- STEP 4: type path to check the path for particular directories.
- STEP 5: type pwd command to view the present working directory.
- STEP 6: is CPU command to check the CPU information.
- STEP 7: stop the process

### SHELL SCRIPTS :

```bash
echo "to find the user" $USER
echo "***********************"
echo "to find the logname" &LOGNAME
echo "***********************"
echo " to find the working shell" $SHELL
echo "**************************"
echo "to find the home directory " $HOME
echo "*******************************"
echo "to find the os type" $OSTYPE
echo "***************************"
echo " to find the present working directory" $(pwd)
echo "*******************************"
echo "to find the cpu info" $(lscpu)
echo "***************************"
echo "to find the free memory space" $(free)
```

## PROGRAM 3

Write a shell script to implement the following of pipes, redirection and the commands.

### PROCEDURE:

- STEP 1 : Start the process.
- STEP 2 : use ( | ) pipe command to link one command with another (or) one operation.
- STEP 3 : use (>>) command to transfer the file from one part into another.
- STEP 4 : use More command to check the information on the screen.
- STEP 5 : display the result on the screen.
- STEP 6 :Save the process.
- STEP 7:End the process

### SHELL SCRIPTS :

```bash
echo "Pipe"
cat file1 | tail -3 |head -1
echo "*********************"
echo "Redirection"
echo "Input Redirection"
ls > hulk
echo "****************"
echo "Output Redirection"
sort < file1
echo "******************"
echo "Tee Command"
cat file1| tail -3 |head -1 | tee mi
```

## PROGRAM 4

Write a shell script for displaying current date user name, file listing and directories using switch case statement.

### PROCEDURE :

- STEP 1 : Start the process.
- STEP 2 : use case statement for performed an different action into an single prompt.
- STEP 3 : declare case variables and case command for the program.
- STEP 4 : if the choice is 1 then the current date will be displayed on the screen.
- STEP 5 : if the choice is 2 then username will be shown .if the choice is three file can be listed and finally if the choice is four directories are displayed on the screen.
- STEP 6 : it none of the choice is met finally default case get executed on the screen.
- STEP 7 : stop the process

### SHELL SCRIPTS :

```bash
while true
do
echo "========== MENU =========="
echo "1. who am i"
echo "2. who logged in"
echo "3. date"
echo "4. calendar"
echo "5. current directory"
echo "6. listing files"
echo "7. Quit"
echo "=========================="
echo "enter your choice"
read n
case $n in
```
1) whoami ;;
2) who ;;
3) date ;;
4) cal ;;
5) pwd ;;
6) ls ;;
7) echo "Exiting... Bye!"
```bash
exit 0 ;;
```
*) echo "Invalid choice. Try again." ;;
```bash
esac
echo "" # just for spacing
done
```

## PROGRAM 5

### Shell script to implement filter commands.

### PROCEDURE:

- STEP 1: Start the process.
- STEP 2: Create a file using vi editor.
- STEP 3: Copy the files /etc/passwd to passwd file.
- STEP 4: To display the lines containing the word home use grep –n "root" passwd
- STEP 5: To display the no.of.lines containing the word root use grep –c "root" passwd
- STEP 6: To display all the lines, words, characters in passwd file use wc passwd
- STEP 7: To display all the lines that don't match with the line root use grep –v "root" passwd.
- STEP 8: To replace ":" with "*" in the file passwd use tr ":" "*" <passwd> statement.
- STEP 9: To display the first column of the file passwd use cut –d ':' –f1 passwd
- STEP 10: The output will be displayed on the screen.
- STEP 11: Stop the process.

### SHELL SCRIPTS :

```bash
echo "fifth program"
echo "Text Line Filters"
grep "India" countries.txt
grep -i "land" countries.txt
sed -n '/A/p' countries.txt
echo "Column/Field Filters"
cut -d',' -f1 countries.txt
echo "Transform/Modify Filters"
sed 's/India/Bharat/g' countries.txt
tr 'a-z' 'A-Z' < countries.txt
tr ' ' '_' < countries.txt
echo "Sort/Unique Filters"
sort countries.txt
sort -r countries.txt
uniq countries.txt
sort countries.txt | uniq -c
echo "Common Filters"
head -5 countries.txt
tail -5 countries.txt
wc -l countries.txt
cp countries.txt myworld
grep "a" countries.txt | sort | head -3
```

## PROGRAM 6

### SHELL SCRIPT TO REMOVE FILE WHICH HAS SIZE AS 0 BYTE

### PROCEDURE:

- STEP 1: Start the process.
- STEP 2: Create a file using vi editor.
- STEP 3: Get the file name as input from the user.
- STEP 4: Using the if..else statement check the condition.
- STEP 5: If the condition of file size as zero means remove the file.
- STEP 6: By using the run command to remove the file.
- STEP 7: Stop the process.

### SHELL SCRIPTS :

```bash
echo "list of files with 0 size"
find /home/ita22 -size 0
echo -n "do you want to delete size 0 files (y/n)?"
read answer
if echo "$answer" |grep -iq "^y";then
find /home/ita22 -size 0 -exec rm {} \;
echo " 0 size files are deleted"
fi
```

## PROGRAM 7

### SHELL SCRIPT TO FIND SUM OF INDIVIDUAL DIGITS

### PROCEDURE:

- STEP 1: Start the process.
- STEP 2: Create a file using vi editor.
- STEP 3: Using echo print the statement.
- STEP 4: Get the file name as input from the user. Declare sum=0.
- STEP 5: By using the while condition print the sum of the individual digits of the given numbers.
- STEP 6: The output will be displayed on the screen.
- STEP 7: Stop the process.

### SHELL SCRIPTS :

```bash
echo "enter a number"
read n
sum=0
while [ $n -gt 0 ] || [ $sum -gt 9 ]
do
if [ $n -eq 0 ]
then
n=$sum
sum=0
fi
sd=$((n%10))
n=$((n/10))
sum=$((sum+sd))
done
echo "the sum of the digits = $sum"
```

## PROGRAM 8

### Shell Script to find greatest among the given number using command line argument.

### PROCEDURE:

- STEP 1: Start the process.
- STEP 2: Create a file using vi editor.
- STEP 3: Using echo print the statement.
- STEP 4: Get the file name as input from the user.
- STEP 5: Using the for loop check the condition and print the numbers stored in the array.
- STEP 6: Using if print the statement as greater and smaller numbers.
- STEP 7: Print the smallest numbers and largest numbers.
- STEP 8: The output will be displayed on the screen.
- STEP 9: Stop the process.

### SHELL SCRIPTS :

```bash
echo "To find the greatest number"
read n1
read n2
read n3
if [ $n1 -gt $n2 ] && [ $n1 -gt $n3 ]
then
echo "$n1 is the greatest of 3 no"
elif [ $n2 -gt $n1 ] && [ $n2 -gt $n3 ]
then
echo "$n2 is the greatest of 3 no"
elif [ $n3 -gt $n1 ] && [ $n3 -gt $n2 ]
then
echo "$n3 is the greatest of 3 no"
fi
```

## PROGRAM 9

### Shell Script for palindrome checking

### PROCEDURE:

- STEP 1: Create a file using vi editor.
- STEP 2:Read the string or number from user .
- STEP 3: In IF statement get the string.
- STEP 4 : Use rev command to reverse the value.
- STEP 5 : Compare the reversed string with original string.
- STEP 6 : Both are equal print that it is a Palindrome otherwise it is not a palindrome.
- STEP 7: Stop the Process.

### SHELL SCRIPT:

```bash
echo "palindrome program"
echo "*****************"
echo "kindly enter a string"
read string
if [ "$(echo $string | rev)" = "$string" ]
then
echo "given string is palindrome"
else
echo "given string is not a palindrome"
fi
```

## PROGRAM 10

### Shell Script to print multiplication table

### PROCEDURE:

- STEP 1: Create a file using vi editor.
- STEP 2: Read the table number n from the user using read command.
- STEP 3: Set the range in For Loop.
- STEP 4: Repeat the statement echo " $i X $n = `expr $n \* $i`" until i less than range using for loop.
- STEP 5: Stop the process.

### SHELL SCRIPT :

```bash
echo "enter the table number"
read n
echo "enter the range"
read range
echo "multiplication table for $n upto the range $range"
for((i=1;i<=range;i++))
```
{
```bash
echo " $i X $n = `expr $n \* $i`" //The loop will be executed until i less than range
```
}

### OUTPUT :

```bash
echo "Enter a number"
read a
for i in {1..10}
do
echo "$i*$a=$(($i*$a))"
done
```

---

or 
```bash
echo "Enter a number" 
read a 
for i in {1..10} 
do 
echo "$i*$a=$(($i*$a))" 
done 
```

## PROGRAM 11

##To write a shell script that displays and analyzes group information: all groups, group ID, 
group members, total group count, and current user's groups.

### PROCEDURE:

STEP 1: Create a shell script file using the vi editor. \n
STEP 2: Use 'cat /etc/group | cut -d: -f1' to display all groups available in the system. 
STEP 3: Accept a group name from the user and use 'getent group' to display its group ID. 
STEP 4: Accept a group name and use 'getent group' to list all users belonging to that group. 
STEP 5: Use 'cat /etc/group | wc -l' to count the total number of groups. 
STEP 6: Use the 'groups' command to display all groups assigned to the current user. 
STEP 7: Stop the process. 

### SHELL SCRIPT :
```bash
echo "Display all groups available in the system" 
cat /etc/group 
echo "Display the group ID of a specified group" 
getent group it30 | cut -d : -f3 
echo "List users belonging to a particular group" 
getent group it30 | cut -d : -f4 
echo "Count the total number of groups available" 
wc -l < /etc/group 
echo "Display groups assigned to the current user" 
groups
```

## PROGRAM 12

Write a shell script to monitor process activities. 
a. Display all running processes. 
b. Display processes belonging to the current user. 
c. Show top five CPU consuming processes. 
d. Display process ID and parent process ID. 
e. Display the total number of running processes. 

### PROCEDURE:
STEP 1: Create a shell script file using the vi editor. 
STEP 2: Use 'ps -ef' to display all running processes in the system. 
STEP 3: Use 'ps -u $USER' to display processes belonging to the current user only. 
STEP 4: Use 'ps -eo pid,comm,%cpu --sort=-%cpu | head -6' to show top 5 CPU consuming 
processes. 
STEP 5: Use 'ps -eo pid,ppid,comm' to display process ID and parent process ID. 
STEP 6: Use 'ps -ef | wc -l' to count total number of running processes. 
STEP 7: Stop the process. 

### SHELL SCRIPT :
```bash
echo "Display all running process" 
ps -e 
echo "Display process belonging to the current user" 
ps -u $(whoami) 
echo "Show top five CPU consuming process" 
ps -eo pid,comm,%cpu-sort=-%cpu|head -6 
echo "Display process ID and parent process ID" 
ps -eo pid,ppid,comm 
echo "Display the total number of running process" 
ps -e h |wc -l
```

## PROGRAM 13

Write a shell script to display network configuration information. 
a. Display system hostname. 
b. Display IP address of all network interfaces. 
c. Display routing table information. 
d. Display DNS server configuration. 
e. Test network connectivity with a remote host.

### PROCEDURE:

STEP 1: Create a shell script file using the vi editor. 
STEP 2: Use 'hostname' command to display the system hostname. 
STEP 3: Use 'ip addr show' to display IP addresses of all network interfaces. 
STEP 4: Use 'ip route' to display the routing table information. 
STEP 5: Use 'cat /etc/resolv.conf' to display DNS server configuration. 
STEP 6: Accept a remote host from the user and use 'ping -c 4' to test connectivity. 
STEP 7: Stop the process. 

### SHELL SCRIPT :
```bash
echo "Display system hostname" 
hostname 
echo "Display IP address of all network interfaces" 
ip addr show 
echo "Display routing table information" 
ip route 
echo "Display DNS server configuration" 
cat /etc/resolve.conf 
echo "Test network connectivity with remote host" 
ping -c 4 google.com
```

## PROGRAM 14

Write a shell script to monitor system logs and detect suspicious activity. 
a. Display recent system log entries. 
b. Display login history of users. 
c. Display failed login attempts. 
d. Search for specific keywords in log files. 
e. Display the last 10 security related log messages. 

### PROCEDURE:

STEP 1: Create a shell script file using the vi editor. 
STEP 2: Use 'tail -20 /var/log/messages' or 'journalctl -n 20' to display recent log entries. 
STEP 3: Use 'last | head -15' to display login history of users. 
STEP 4: Use grep to search for 'Failed password' in /var/log/secure to find failed login 
attempts. 
STEP 5: Accept a keyword from the user and search for it in log files using grep. 
STEP 6: Use 'tail -10 /var/log/secure' to display the last 10 security-related log messages. 
STEP 7: Stop the process. 

### SHELL SCRIPT :
```bash
touch ~/mylog.log 
echo "$(date)-INFO-User Logged In">>~/mylog.log 
echo "$(date)-INFO-User Opened Application">>~/mylog.log 
echo "$(date)-WARNING-Incorrect Password Entered">>~/mylog.log 
echo "$(date)-INFO-User Logged OUT">>~/mylog.log 
tail -f ~/mylog.log 
last | tail -10 
grep WARNING mylog.log 
grep INFO mylog.log 
```

## PROGRAM 15

Write a shell script to analyze disk usage. 
a. Display disk usage of all directories in the home folder. 
b. Display the top 5 largest directories in the system. 
c. Display the number of files in each directory. 
d. Display the file system type of each partition. 
e. Display free disk space available. 

### PROCEDURE:

STEP 1: Create a shell script file using the vi editor. 
STEP 2: Use 'du -sh ~/*' to display disk usage of all directories inside the home folder. 
STEP 3: Use 'du -sh /* | sort -rh | head -5' to find the top 5 largest directories in the system. 
STEP 4: Use a for loop with 'ls | wc -l' inside each subdirectory to count the number of files. 
STEP 5: Use 'df -T' to display the filesystem type of each mounted partition. 
STEP 6: Use 'df -h' to display free disk space available on all partitions. 
STEP 7: Stop the process.

### SHELL SCRIPT :
```bash
echo "--Disk usage of Home Directory--"                                                                                                         
du -sh ~/* 2>/dev/null                                                                                                                          
echo " "                                                                                                                                        
echo "---Top 5 largest Directories--"                                                                                                           
du -sh /* 2>/dev/null | sort -rh | head -5                                                                                                      
echo " "                                                                                                                                        
echo "--File count in Each Home Subdirectory--"                                                                                                
for dir in ~/*/                                                                                                                                 
do                                                                                                                                              
count=$(ls "$dir" 2>/dev/null | wc -l)                                                                                                          
echo "$dir:$count files"                                                                                                                        
done                                                                                                                                            
echo " "                                                                                                                                        
echo "--File System Type of each partition--"                                                                                                   
df -T | awk '{print $1,$2,$NF}'                                                                                                                 
echo " "                                                                                                                                        
echo "--- Free Disk Space Available ---"                                                                                                    
df -h
```

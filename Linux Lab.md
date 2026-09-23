PROGRAM 1: Basic Linux commands: rm, cp, cat, mv, cmp, wc, split, diff.


ls 
cp file1 file2 
cat file2 
mv file3 file4 
cat file4 
wc file1 
wc -l file1 
wc -w file1 
wc -c file1 
split -3 file1 
head -3 file1 
tail -3 file1
cmp file1 file2 
diff file1 file2
rm file6
rm -r * 

PROGRAM 2: Write a shell script to implement the user and System information by commands.


echo "to find the user" $USER
echo "***********************"
echo "to find the logname" &LOGNAME
echo "***********************"
echo " to find the working shell" $SHELL
echo "**************************"
echo "to find the home directory " $HOME
echo "*******************************"
echo  "to find the os type"  $OSTYPE
echo "***************************"
echo " to find the present working directory" $(pwd)
echo "*******************************"
echo "to find the cpu info" $(lscpu)
echo "***************************"
echo "to find the free memory space" $(free)

PROGRAM  3 : Write a shell script to implement the following of pipes, redirection and the commands.

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


PROGRAM 4: Write a shell script for displaying current date user name, file listing and directories using switch case statement.


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
        1) whoami ;;
        2) who ;;
        3) date ;;
        4) cal ;;
        5) pwd ;;
        6) ls ;;
        7) echo "Exiting... Bye!"
           exit 0 ;;
        *) echo "Invalid choice. Try again." ;;
    esac
    echo ""  # just for spacing
done


PROGRAM 5: Shell script to implement filter commands.


echo "fifth program"
echo “Text Line Filters"
grep "India" countries.txt
grep -i "land" countries.txt
sed -n '/A/p' countries.txt
echo “Column/Field Filters”
cut -d',' -f1 countries.txt
echo “Transform/Modify Filters”
sed 's/India/Bharat/g' countries.txt
tr 'a-z' 'A-Z' < countries.txt
tr ' ' '_' < countries.txt
echo “Sort/Unique Filters”
sort countries.txt
sort -r countries.txt
uniq countries.txt
sort countries.txt | uniq -c
echo “Common Filters”
head -5 countries.txt
tail -5 countries.txt
wc -l countries.txt
cp countries.txt myworld
grep "a" countries.txt | sort | head -3


PROGRAM 6: SHELL SCRIPT TO REMOVE FILE WHICH HAS SIZE AS 0 BYTE


echo "list of files with 0 size"
find /home/ita22 -size 0
echo -n "do you want to delete size 0 files (y/n)?"
read answer
if echo "$answer" |grep -iq "^y";then
find /home/ita22 -size 0 -exec rm {} \;
echo " 0 size files are deleted"
fi


PROGRAM 7: SHELL SCRIPT TO FIND SUM OF INDIVIDUAL DIGITS


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


PROGRAM  8: Shell Script to find greatest among the given number using command  line  argument.


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


PROGRAM 9: Shell Script for palindrome checking 


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


PROGRAM 10: Shell Script to print multiplication table 


echo "enter the table number"
read n
echo "enter the range"
read range
echo "multiplication table for $n upto the range $range"
for((i=1;i<=range;i++))
{
  echo " $i X $n = `expr $n \* $i`" //The loop will be executed until i  less than range
}


PROGRAM 11: 
Write a shell script to display and analyze group information. 
a. Display all groups available in the system. 
b. Display the group ID of a specified group. 
c. List users belonging to a particular group. 
d. Count the total number of groups available. 
e. Display groups assigned to the current user.


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


PROGRAM 12: 
Write a shell script to monitor process activities. 
a. Display all running processes. 
b. Display processes belonging to the current user. 
c. Show top five CPU consuming processes. 
d. Display process ID and parent process ID. 
e. Display the total number of running processes.


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


PROGRAM 13: 
Write a shell script to display network configuration information. 
a. Display system hostname. 
b. Display IP address of all network interfaces. 
c. Display routing table information. 
d. Display DNS server configuration. 
e. Test network connectivity with a remote host. 


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


Program 14: 
Write a shell script to monitor system logs and detect suspicious activity. 
a. Display recent system log entries. 
b. Display login history of users. 
c. Display failed login attempts. 
d. Search for specific keywords in log files. 
e. Display the last 10 security related log messages. 


touch ~/mylog.log 
echo "$(date)-INFO-User Logged In">>~/mylog.log 
echo "$(date)-INFO-User Opened Application">>~/mylog.log 
echo "$(date)-WARNING-Incorrect Password Entered">>~/mylog.log 
echo "$(date)-INFO-User Logged OUT">>~/mylog.log 
tail -f ~/mylog.log 
last | tail -10 
grep WARNING mylog.log 
grep INFO mylog.log 



PROGRAM 15: 
Write a shell script to analyze disk usage. 
a. Display disk usage of all directories in the home folder. 
b. Display the top 5 largest directories in the system. 
c. Display the number of files in each directory. 
d. Display the file system type of each partition. 
e. Display free disk space available. 


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
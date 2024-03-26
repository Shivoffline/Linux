# Linux
all linux docs

Linux commands:

absolute and relative path 
Kernel level commands  
-R and -r 
Permissions - chmod 

==================================
ls
pwd 
date
cd
cp
mv
rm
rmdir
mkdir
clear
touch
ln  -> hard and soft link 
cal 
expr 
passwd 
who
whoami
man 
help 
tree 
=============================================================================================
basic commands

ls     -directory listing

ls -al -listing with hidden files

cd dir -change directory to dir

pwd    –show current directory

mkdir dir – create a directory dir

rm file – delete file

rm -r dir – delete directory dir

rm -f file – force remove file

rm -rf dir – force remove directory dir *

cp file1 file2 – copy file1 to file2

cp -r dir1 dir2 – copy dir1 to dir2; create dir2 if not exists

mv file1 file2 – rename or move file1 to file2

if file2 is an existing directory, moves file1 into file2

ln -s file link – create symbolic link link to file

stat file – display file attributes

touch file – create or update file

cat > file – places standard input into file

more file – output the contents of file

head file – output the first 10 lines of file

tail file – output the last 10 lines of file

tail -f file – output the contents of file as it grows, startingith the last 10 lines
=====================================

ls - lists the contents of your current working directory.

   some options are :
      -l   : list in long format
	  -a   : all files including those which begin with dot  ( hidden directory showing )
	  -F   : It is used to classify the directories, executables.
	  -i   : list the inode number in the first column.
	  -R   : Recursively list all directories and subdirectories 
	  -r   : dispaly in reverse order
	  -t   : sorts files by access time
	  -d   : shows the names of directoies and not their contents
	  -h   : Indicates human readable 
	  -S   : Sorts files by file size.



apt: package manager for ubuntu, like it will manage the package installation,update,upgrade,remove etc...
 
 sudo apt update 
 sudo apt upgrade 
 sudo apt install <packagename>
 sudo apt remove <packagename>
 
 sudo apt download <packagename>
 sudo dpkg -i *.deb

  list - list packages based on package names
  search - search in package descriptions
  show - show package details
  install - install packages
  reinstall - reinstall packages
  remove - remove packages
  purge - remove the package and configuration files 
  autoremove - Remove automatically all unused packages
  update - update list of available packages
  upgrade - upgrade the system by installing/upgrading packages
  full-upgrade - upgrade the system by removing/installing/upgrading packages
  edit-sources - edit the source information file
  satisfy - satisfy dependency strings
  
  ------------------------------------
  cd : To change working directory
  cd <<dir>>
  cd <<path/dir>>
  
  cd /  : takes to home directory
  cd <dirname>
  cd <pathname>
  cd ..  to move one level up 
  cd ../.. to move two level up
  cd ~  It will takes to home dir 
  cd    it will takes to home directory
  cd -  it will takes to home directory
  
  Absolute path begins with the root directory. = 
  Relative path starts from the current working directory.
  
 ----------------------------------------------------------------
 rmdir : removes a dir
        > Must be empty before it is deleted.
		> 
		-i > interactively asks for confirming the deletion of files.
		-r > recursively
		
--------------------------------------------------------------------------
hardlink                                                                                softlink
---------                                                            -------------------------------------------------
Both inode number for hardlink & orginal file and same.           >  Here both orginal & softlink inode number different.
ln <originalfile> <newhardlinkname/path>                              ln -s <originalfile> <newsoftlinkname/path>
If original file deleted, then handlink file still working        >  If original file deleted ,then softlink will not work.
Both file has same size and same permissions.                     > original file permission also differnce in softlink.
                                                                  > -rw-r--r--  1 root root    1474 Feb  6 10:38 passwd                                                                 
																  >  lrwxrwxrwx  1 root       root         11 Feb  7 09:19 passwd.txt -> /etc/passwd
------------------------------------------------------------------------------------------------------------------------------------------------------
cp command :

copy the file or folder one location to another location in linux.

cp <sourcefile>  <destinationfilelocation>
cp <sourcepath/file>   <destpath/file>
cp -R <pathoffolder>  <destpathoffolder>

cp -i <source> <dest>   (   -i, --interactive )
                         (  -f, --force )

--------------------------------------------------------------------------
touch - change file timestamps
 Mandatory arguments to long options are mandatory for short options too.

       -a     change only the access time

       -c, --no-create
              do not create any files

       -d, --date=STRING
              parse STRING and use it instead of current time

       -f     (ignored)

       -h, --no-dereference
              affect each symbolic link instead of any referenced file (useful only on systems that can change the timestamps  of
              a symlink)

       -m     change only the modification time

       -r, --reference=FILE
              use this file's times instead of current time

       -t STAMP
              use [[CC]YY]MMDDhhmm[.ss] instead of current time

       --time=WORD
              change  the  specified time: WORD is access, atime, or use: equivalent to -a WORD is modify or mtime: equivalent to
              -m

       --help display this help and exit

Otheruser creating for file & directory, bydefault persmission:
drwxrwxr-x 2 avinna1234 avinna1234     4096 Feb  7 09:50 data1/   > for folder 775
-rw-r--r-- 1 avinna1234 avinna1234        0 Feb  7 10:26 data9.txt > for file 644

Root user creating for file and directory, Bydefault permission:
-rw-r--r--  1 root root    0 Feb  7 10:29 data.txt  > for file 644
drwxr-xr-x  2 root root 4096 Feb  7 10:29 data4/    > for folder 755

   
	   
rm  - remove files or directories
---------------------------
rm <filename>
rm -r <foldername>
rm -rf  <folder>  ( forcefully)
	
Uses the * wildcard to represent all files and directories matching a pattern.

-----------------------------------
rmdir - remove empty directories

rmdir <emptyfoldername>
                -p, --parents
				-v, --verbose
				-r, -R, --recursive
              remove directories and their contents recursively
               -d, --dir
                 remove empty directories
---------------------------------------------------------------------------------
mkdir - make directories

 -m, --mode=MODE
              set file mode (as in chmod), not a=rwx - umask

       -p, --parents
              no error if existing, make parent directories as needed

       -v, --verbose
              print a message for each created directory

       -Z     set SELinux security context of each created directory to the default type
----------------------------------------------------------------------------------------------
 who - show who is logged on
 
       -a, --all
              same as -b -d --login -p -r -t -T -u

       -b, --boot
              time of last system boot

       -d, --dead
              print dead processes

       -H, --heading
              print line of column headings

       --ips  print  ips  instead of hostnames. with --lookup, canonicalizes based on stored IP, if available, rather than stored
              hostname

       -l, --login
              print system login processes

       --lookup
              attempt to canonicalize hostnames via DNS	  
       
       -m     only hostname and user associated with stdin

       -p, --process
              print active processes spawned by init

       -q, --count
              all login names and number of users logged on

       -r, --runlevel
              print current runlevel

       -s, --short
              print only name, line, and time (default)

       -t, --time
              print last system clock change

       -T, -w, --mesg
              add user's message status as +, - or ?

       -u, --users
              list users logged in

       --message
              same as -T

       --writable
              same as -T

       --help display this help and exit	
-----------------------------------------------
 whoami - print effective userid
 
 ----------------------------------------------------
 clear - clear the terminal screen
 
 
OPTIONS
       -T type
            indicates the type of terminal.  Normally this option is unnecessary, because the default is taken from the  environ‐
            ment variable TERM.  If -T is specified, then the shell variables LINES and COLUMNS will also be ignored.

       -V   reports the version of ncurses which was used in this program, and exits.  The options are as follows:

       -x   do not attempt to clear the terminal's scrollback buffer using the extended “E3” capability.
----------------------------------------------------------------------------------------------------------------------

df, du, free, lscpu, uname, hostname, chmod, chown, lsblk, ps, top, kill, ping, grep, find, sed , awk 

1. df -> command displays information about file system disk space usage on the mounted file system

This command retrieves the information from `/proc/mounts` or `/etc/mtab`. 
By default, df command shows disk space in Kilobytes (KB) and uses the SI unit suffixes 
(e.g, M for megabytes, G for gigabytes) for clarity.

df -a   = Includes pseudo, duplicate, and inaccessible file systems in the output
df -h	= Prints sizes in a human-readable format using power of 1024.
df -i	= Lists inode information instead of block usage.

Inodes keep track of all the files on a Linux system.
Linux® must allocate an index node (inode) for every file and directory in the filesystem. Inodes do not store actual data. 
Instead, they store the metadata where you can find the storage blocks of each file's data.

df -l	= Limits listing to local file systems.
df -P	= Uses POSIX output format for better portability.
df -T	= display file type 

2. du  -> powerful utility that allows users to analyze and report on disk usage within directories and files.

du -a	List all files and directories size
du -h	Display in human readable format
du -c	Display grand total in the output
du -s	Display only total
du -0/td>	End output with null byte
du --block-size=<size>	Specify block size
du --time	Display time modification

3. free command gives information about used and unused memory usage and swap memory of a system. 
By default, it displays memory in kb (kilobytes)
Memory mainly consists of RAM (random access memory) and swap memory.

free -b     display information in Bytes  
free -m     display information in Megabytes  
free -g     display information in Gigabytes  
free -t	Display total memory
free -o	Disable buffer adjusted line
free -s <time>	To update RAM at regular intervals
free -l	Display high and low memory size statistics

4. lscpu :

The lscpu command, short for list CPU, provides a detailed list of information about the CPUs in the system. 
This includes the CPU number, architecture, vendor, family, model, and CPU caches.

lscpu -e = Displays the CPU information in human-readable format. Displays only one column of details when used with the column name.
lscpu -p = Printing Info in Parsing-Friendly Mode
lscpu -be  = Limiting Output to Online or Offline Mode
lscpu -J = Display Output in JSON Format
lscpu -C = Printing Info about Caches
lscpu --output-all -e = Show Detailed Output About All Available Columns

Ping:

PING (Packet Internet Groper) command is used to check the network connectivity between host and server/host.
This command takes as input the IP address or the URL and sends a data packet to the specified address
with the message “PING” and get a response from the server/host this time is recorded which is called latency.

Ping uses ICMP(Internet Control Message Protocol) to send an ICMP echo message to the specified host
 if that host is available then it sends ICMP reply message.
 
define the number of packets to send to the server/host by using -c option :
 
ping -c 2 google.com 

Kill:

kill command in Linux (located in /bin/kill), is a built-in command which is used to terminate processes manually. 
kill command sends a signal to a process that terminates the process. 
If the user doesn’t specify any signal that is to be sent along with the kill command,
 then a default TERM signal is sent that terminates the process.
 
kill -l = To find signal numbers

kill -9 1212

SIGHUP	1	It hangup detected on controlling terminals or death of controlling process.
SIGINT	2	It interrupts from keyboard.
SIGKILL	9	It kills signal.
SIGTERM	15	It terminates signal.

Top:

The top command is used for memory monitoring. It works only on Linux platform. 
The top command produces an ordered list of running processes selected by user-specified criteria, and updates it periodically. 
By default, ordering is by CPU usage, and it shows processes that consume maximum CPU.

top -n 10  = will automatically exit after 10 number of repetition.
top -u root  = Display Specific User Process 

ps:

ps command provides a snapshot of the current running processes on your system.

a	= List all running processes for all users.

-A, -e	= Lists all processes on the entire system, offering a complete overview of running tasks and programs.

-a	= List all processes except session leaders (instances where the process ID is the same as the session ID) and processes not associated with a terminal.

-d	= Lists all processes except session leaders, providing a filtered view of processes running on the system.

--deselect, -N	= Lists all processes except those that meet specific user-defined conditions.

f	= Displays the hierarchy of processes in a visual ASCII art format, illustrating parent-child relationships.

-j	= Presents the output in the jobs format, providing detailed information such as process ID, session ID, and command.

T	= Lists all processes associated with the current terminal, aiding in focusing on tasks related to a specific terminal.

r	= Only lists running processes, useful for monitoring system performance.

u	= Expands the output to include additional information like CPU and memory usage.

-u   = Specifies a username, listing processes associated with that user.

x  = Includes processes without a TTY, showing background processes not tied to a specific terminal session.

lsblk:

Lsblk is used to display details about block devices and these block devices(Except ram disk) are basically those files
 that represent devices connected to the pc.
 
display a hierarchical view of all block devices connected to your system, including information about partitions and mount points.

lsblk -a = Display All Devices, Including Empty Ones
lsblk -b = Print sizes in bytes 
lsblk -t = Viewing Devices in a Tree-Like Format
lsblk -m = display all details of device owner, group and mode of block devices. 

 
hostname:

hostname command in Linux is used to obtain the DNS (Domain Name System) name 
and set the system’s hostname or NIS (Network Information System) domain name

hostname -a = Display all aliases of the host.
hostname -i = Display the IP address of the host
hostname -I = used to get all IP (network) addresses. 
hostname -V = version information about the hostname 
sudo hostname NEW_HOSTNAME = change new hostname


Uname:

“uname” stands for “Unix Name,” and the command itself is designed to provide you with key details about your Linux system.

uname  -a = prints all the system information in the following order: Kernel name, network node hostname, kernel release date, kernel version, machine hardware name
			, hardware platform, operating system.
			
uname  -s = It prints the kernel name.

uname  -n = prints the hostname of the network node(current computer).
uname  -r = It prints the kernel release date.
uname -m = prints the machine hardware name.
uname  -o = print OS  details 

-------------------------

find :

https://www.geeksforgeeks.org/find-command-in-linux-with-examples/

1. Find a single file by name:

$ find / -name "Foo.txt" 2>/dev/null
/home/seth/Documents/Foo.txt

2>/dev/null: all the errors that come from the find command are being redirected to /dev/null meaning they won't be displayed in the output


2. Find a single file by approximate name

$ find / -iname "*foo*txt" 2>/dev/null
/home/seth/Documents/Foo.txt
/home/seth/Documents/foo.txt
/home/seth/Documents/foobar.txt

3. Find everything:

$ find ~/Documents -ls
3554235 0 drwxr-xr-x [...] 05:36 /home/seth/Documents/

4. Find by content:

 root@DESKTOP-O5SG2A8:~# find ~/demo/ -name "*txt" -exec grep shiv {} \;
i hi this is shiva
shiv mahadev

root@DESKTOP-O5SG2A8:~# find ~/demo/ -name "*txt" -exec grep -Hi shiv {} \;
/root/demo/File1.txt:i hi this is shiva
/root/demo/File1.txt:shiv mahadev

5. Find files by type?:

You can display files, directories, symlinks, named pipes, sockets, and more using the -type option.

root@DESKTOP-O5SG2A8:~# find ~ -type f
/root/file1.txt
/root/.cache/motd.legal-displayed
/root/File1.txt
/root/.Xauthority
/root/.profile
/root/demo/file1.txt
/root/demo/File1.txt
/root/.bash_history
/root/file2.txt
/root/sample.txt
/root/.motd_shown
/root/.viminfo
/root/.wsl-config
/root/.lesshst
/root/.bashrc


6. List just directories


root@DESKTOP-O5SG2A8:~# find ~ /root/  -type d
/root
/root/snap
/root/snap/ubuntu-desktop-installer
/root/snap/ubuntu-desktop-installer/1276
/root/snap/ubuntu-desktop-installer/1284
/root/snap/ubuntu-desktop-installer/common

7. Limit listing results

$ find ~/Public/ -maxdepth 1 -type d
/home/seth/Public/
/home/seth/Public/example.com

8. Find empty files
Sometimes it's helpful to discover empty files as a way to declutter:

$ find ~ -type f -empty
random.idea.txt

9. Find files by age

$ find /var/log -iname "*~" -o -iname "*log*" -mtime +30

10. Search a path

find / -type d -name 'demo*' 2>/dev/null
/root/demo
/mnt/c/Program Files/Git/mingw64/lib/tk8.6/demos


-atime & -mtime 

Search Multi file names:


find . -type f \ ( -name "*sh" -o -name "*.txt" \ ) 
			
================================================================================================================

Shell scripting:

#! -> Shebang 
/bash -> executable used to execute the shell script 
#!/bin/bash -> default used syntax

man command 

chmod -> grand permissions

User, Group, Everyone 

4-> read
2-> write
1-> execute 

chmod 777 

commands:
History  
nproc
free 
top
df -h
ps -ef 

Instead of "echo" use "set -x"
set -x  -> debug mode 

date | echo "date is"

Output:  date is

stdin stdout - channels or log flows in VMs
date is a system default command.
It sends the output to the pipe will not be able to receive the information from stdin.
If the command is not ready to send the info to stdin.  

===============================

set -e   -> It exits the script when there is error

set -o pipefail   -> exits the script if an error while using pipe 

logfile   -> find errors in logfile 

curl  -> retrieve information from any website/link.
         transfer URL 
		 
		 curl <URL>
		 
enables data exchange between a device and a server through a terminal.

wget -> download URL file 

trap -> trapping signals 

================
1. To list all processes:

awk -> filter the output of a particular string
ps -ef | awk -F" '{print $4}'

2. Print only errors from a remote log:

curl <link> | grep TRACE 

3. Print numbers divided by 3 & 5 and not 15:

divisible by 3, div by 5, not 3*5=15

for i in {1..100}; do 
if ([ expr $i % 3 == 0 ] || [ expr $i % 5 == 0 ])) && [ expr $i % 15 != 0 ];
then
		echo $i
fi;
done

for ((i = 1; i <= 100; i++)); do
    # Check if the number is divisible by 3 and 5 but not 15
    if ((i % 3 == 0)) && ((i % 5 == 0)) && ((i % 15 != 0)); then
        echo $i
    fi
done

4. print number of "S" in "mississippi"

x=mississipi

grep -o "s" <<<"$x" | wc -l 

5. How to debug the shell script:

set -x

6. Crontab in linux and its usage:

It acts like an alarm to set up in linux for execution for any process/task.

7. How to open a read only file:

vim -r test.txt

8. Diff Soft and Hard link:

A hard link always points a filename to data on a storage device. 
A soft link always points a filename to another filename, which then points to information on a storage device.

9. Diff Break and continue statement:

Break -> Breaking the execution
Continue -> Continuing the execution (Skip)

10. Disadvantages of Shell scripting:

- Execution speed is slow

11. Different types of loops:

While
For
Until

12. Is Bash dynamic or Statically typed?

Dynamically typed. 

In dynamically typed languages, the type of a variable is interpreted at runtime, and the type of a variable can change during the execution of the program.

13. Network Troubleshooting utilty:

traceroute google.com 

14. Sort list of files:

sort command

15. Manage logs of a sys generate huge log files everyday:

logrotate 

=========================================================


 Advanced Linux Networking commands:

1. ifconfig:

Linux ifconfig stands for interface configurator. It is one of the most basic commands used in network inspection. 

ifconfig is used to initialize an interface, configure it with an IP address, and enable or disable it. 

It is also used to display the route and the network interface. 

Basic information displayed upon using ifconfig are:

IP address
MAC address
MTU(Maximum Transmission Unit) 

ifconfig eth0
ifconfig lo

To assign an IP address and Gateway to an interface

To enable an interface : 	ifup eth0 

To disable an interface: 	ifdown eth0 


2. ip :

This is the latest and updated version of ifconfig command and used to get the details of a specific interface.

ip a 
ip addr


3. traceroute: 

Linux traceroute is one of the most useful commands in networking. 
It is used to troubleshoot the network. It detects the delay and determines the pathway to your target.

traceroute <destination>


$ traceroute google.com

The output provides the following information:

The specified hostname
Size of the packets
The maximum number of hops required.
The IP address.

4.tracepath:

Linux tracepath is similar to traceroute command. It is used to detect network delays. However, it doesn't require root privileges.

It traces the route to the specified destination and identifies each hop in it. 
If your network is weak, it recognizes the point where the network is weak.

tracepath <destination> 

5. Ping: 

Linux ping is one of the most used network troubleshooting commands. It basically checks for the network connectivity between two nodes.

ping stands for Packet INternet Groper.

The ping command sends the ICMP echo request to check the network connectivity.

$ ping google.com

$ ping -D google.com   -> Shows detailed Timestamp

ping -c 4 google.com   ->  limit the packets up to 4.


6. netstat

Linux netstat command refers to the network statistics. 

It provides statistical figures about different interfaces which include open sockets, routing tables, and connection information.

 To display the programs with the open socket:
 
 netstat -p

 To get the details of the ports:
 
 netstat -s

 To get the information of the routing table:
 
 netstat -r


7.ss
Linux ss command is the replacement for netstat command. It is regarded as a much faster and more informative command than netstat.

The faster response of ss is possible as it fetches all the information from within the kernel userspace. 

Listing listening and connected ports of TCP, UDP and Unix: 

If you want to list connected as well as listening ports for TCP, UDP and Unix use -t, -u and -x respectively with a command.

ss -ta  
ss -ua  
ss -xa  

Listing listening Ports of TCP, UDP and Unix: 

If you want to list listening ports for TCP, UDP and Unix use -t, -u and -x respectively with l command.

ss -lt  
ss -lu  
ss -lx  

8.dig
Linux dig command stands for Domain Information Groper. This command is used in DNS lookup to query the DNS name server. It is also used to troubleshoot DNS related issues.

It is mainly used to verify DNS mappings, MX Records, host addresses, and all other DNS records for a better understanding of the DNS topography.

dig command outputs the A records by default. If you want to specifically search for MX or NS type, use the syntax below.

 $ dig google.com MX

 $ dig google.com ANY


9.nslookup

Linux nslookup is also a command used for DNS related queries.

10.route

Linux route command displays and manipulates the routing table existing for your system.

A router is basically used to find the best way to send the packets across to a destination.

Displaying numerical IP address

	route -n

Routing cache information

	route -Cn  

11.host

Linux host command displays the domain name for a given IP address and IP address for a given hostname.

It is also used to fetch DNS lookup for DNS related query.


12.arp

Linux arp command stands for Address Resolution Protocol. It is used to view and add content to the kernel's ARP table.

arp

arp -n

13.iwconfig

Linux iwconfig is used to configure the wireless network interface. It is used to set and view the basic WI-FI details like SSID and encryption.

14.hostname

Linux hostname is the simple command used to view and set the hostname of a system

To set the hostname:

 sudo hostname <newName>

15. curl & wget:

Linux curl and wget commands are used in downloading files from the internet through CLI. 

The curl command has to be used with the option "O" to fetch the file, while the wget command is used directly.

curl -O google.com/doodles/childrens-day-2014-multiple-countries  


wget google.com/doodles/childrens-day-2014-multiple-countries  


16.mtr:

Linux mtr command is a combination of ping and the traceroute command. 
It continuously displays information regarding the packets sent with the ping time of each hop. 
It is also used to view the network issues.

mtr google.com


17.whois:

Linux whois command is used to fetch all the information related to a website. 

You can get all the information about a website including the registration and the owner information.

whois google.com 

18.ifplugstatus
Linux ifplugstatus command is used to check if a cable is plugged into the network interface. 


19.iftop
Linux iftop command is used in traffic monitoring. 

20.tcpdump:

Linux tcpdump command is the most used command in network analysis among other Linux network commands. It captures the traffic that is passing through the network interface and displays it. 

This kind of access to the packet will be crucial when troubleshooting the network.

yum install tcpdump


sudo tcpdump

This will capture the packets from the current interface of the network through which the system is connected to the internet. 

ifconfig 

To capture packets from a specific network interface = sudo tcpdump -i eth0
 
 This command will now capture the packets from eth0 network interface. 


sudo tcpdump -D

To display all available interfaces







==============================================================================
Sree:

What is the awk command in Linux, and how is it used for text processing with example?
How can you extract the text between two specific patterns in a file using sed?
How does the sort command work, and how can you use it to sort a file numerically?
What is the tr command used for, and provide an example of its usage.
Explain the difference between the kill and kill -9 commands when terminating processes.
Describe the purpose of the top command in Linux, and provide examples of its usage.
Explain the role of the iptables command in managing firewall rules with examples.
What is the difference between TCP and UDP, and when would you use one over the other?
Explain how to pause and resume processes using the Ctrl-Z, bg, and fg commands. Example ?
How can you configure a Linux system as a DHCP server to assign IP addresses to clients?



Hari:

Explain the differences between grep, sed, and awk with proper examples.
What is the purpose of the uniq command in text processing? How does it remove duplicate lines?
Explain the difference between wc -l and wc -w commands in Linux.
What is the purpose of the ps command, and how can you list all processes running under a specific user?
How do you use the nohup command to run a process in the background even after closing the terminal?
How can you find the process ID (PID) of a running process using the pgrep command?
How can you display the routing table in Linux using the netstat or ip route command? Show the difference?
What is port forwarding, and how do you set it up using iptables?
Explain the purpose of the traceroute command and how it works to trace the path of network packets.
Describe the use of the ss command in displaying socket statistics in Linux with example?

============================================================================================

#!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd 
systemctl enable httpd 
echo "Hello World" > /var/www/html/index.html 


=========================================================================================









		 







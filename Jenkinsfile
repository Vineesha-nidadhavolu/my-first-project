Install jenkins using bash script:
----------------------------------
#!/bin/bash
command=/var/lib/jenkins
if [ -f $command ]
then
   echo "$command is available, let's run it...."
else
   echo "$command is not available, installing it...."
   sudo apt update
   sudo apt install fontconfig openjdk-17-jre -y
   java -version
   sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
   https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
  
  echo deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
  
  sudo apt-get update
  sudo apt-get install jenkins -y
  sudo systemctl enable jenkins
  sudo systemctl start jenkins
  sudo cat /var/lib/jenkins/secrets/initialAdminPassword
fi
------------------------------------------------------------------
#!/bin/bash
myvar=1
while [ $myvar -le 20 ]
do
echo $myvar
myvar=$(( $myvar +1 ))
sleep 0.5
done
----------------------------------------------------------------
#!/bin/bash
command=/var/lib/jenkins
if [ -f $command ]
then
   echo "$command is available, let's run it...."
else
   echo "$command is not available, installing it...."
   sudo apt update
   sudo apt install maven -y
   mvn -v
fi
-----------------------------------------------------------
#!/bin/bash

myfun () {
    echo "hello world from mahesh"
}
--------------------------------------------------
#!/bin/bash
add_two_num () {
    local sum = $(( $1 + $2 ))
	echo "sum of $1 and $2 is $num"
}
add_two_num 2 3
----------------------------------
 #!/bin/bash
release_file=/etc/os-release
if grep -q "Arch" $release_file
then
   #the host name is based on Arch, run the pacman update command
   sudo pacman -Syu
 fi

if grep -q "pop" $release_file || grep -q "ubuntu" $release_file
then
   #the host is based on debian or ubuntu
   #run the apt version of the command
   sudo apt update
   sudo apt dist-upgrade 
fi
-------------------------------------------------
#!/bin/bash
if [ -d /etc/pacman.d ]
then
   #the host is based on Arch, run the pacman update command
   sudo pacman -Syu
fi
if [ -d /etc/apt ]
then
   #the host is based on debian or ubuntu
   # run the apt version of the command
   sudo apt update
   sudo apt dist-upgrade
fi   
----------------------------------------------
#!/bin/bash
var1=10
var2=20

addition=`expr $var1 + $var2`
subtraction=`expr $var1 - $var2`
multiplication=`expr $var1 \* $var2`
divide=` expr $var1 / $var2`
echo "addition is: $addition"
echo "subtraction is: $subtraction"
echo "multiplication is: $multiplication"
echo "divid is: $divide"
---------------------------------------------------
for loop:
#!/bin/bash
for current_number in 1 2 3 4 5 6 7 8 9 10
do
echo $current_number
sleep 1
done
echo "this is outside of the for loop"
---------------------------------------------------
#!/bin/bash
for n in {1..10}
do
echo $n
sleep 1
done
echo "this is outside of the for loop."
-------------------------------------------------
mkdir logfiles
cp /var/log/*.log logfiles/
ls logfiles/
touch logfiles/logfile.txt
ls logfiles/
nano logfile.sh
-------------------------
#!/bin/bash
for file in logfiles/*.log
do
 tar -czvf $file.tar.gz $file
done
------------------------------
ls
chmod +x logfile.sh
ls
./logfile.sh
---------------------------------
#!/bin/bash
command=/var/lib/docker
if [ -f $command ]
then
   echo "$command is available, let's run it...."
else
   echo "$command is not available, installing it...."
   curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
   echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
   sudo apt-get install apt-transport-https ca-certificates curl gnupg lsb-release -y
   sudo apt-get update
   sudo apt-get install docker-ce docker-ce-cli containerd.io -y
   docker version
   sudo usermod -aG docker $USER
   sudo systemctl daemon-reload
   sudo service docker stop
   sudo service docker start 
fi
-------------------------------------------------------
arguments:
#!/bin/bash
lines=$(ls -lh $1 | wc -l)
echo "you have $(($lines-1)) objects in the $1 directory."

./arguments.sh /etc 
result: you have 193 objects in the /etc directory
-------------------------------------------------------
lines=$(ls -lh /etc | wc -l)
ls -l /etc | ec -l find the noof objects in the /etc directory
ls -l /etc | head
-----------------------------------------------
#!/bin/bash
lines=$(ls -lh $1 | wc -l)

if [ $# -ne 1 ]
then
   echo "this script requires exactly one directory path passed to it."
   echo "please try again."
   exit 1
fi
   
echo "you have $(($lines-1)) objects in the $1 directory."
------------------------------------------------------------
Back up script:
#!/bin/bash

# Check to make sure the user has entered exactly two arguments.
if [ $# -ne 2 ]
then
   echo "Usage: backup.sh <source_directory> <target_directory>"
   echo "Please try again"
   exit 1
fi

# Check to see if rsync is installed.
if ! command -v rsync > /dev/null 2>&1
then
   echo "this script requires rsync to be installed."
   echo "please use your distribution's package manager to install."
   exit 2
fi

# capture the current date, and store it in the format YYYY-MM-DD.
current_date=$(date +%Y-%m-%d)
rsync_options="-avb --backup-dir $2/$current_date --delete --dry-run"
$(which rsync) $rsync_options $1 $2/current >> backup_$current_date.log
-----------------------------------------------------
nano backup.sh
mkdir backup
ls
./backup.sh pictures/ backup/
cat backup_2023-12-12.log
ls backup/current/
touch pictures/textfile.txt
touch pictures/chroma.png
touch pictures/newfile.txt
rm -rf backup_2023-12-12.log
./backup.sh pictures/ backup/
ls backup/current/backup/2023-12-12/
---------------------------------------------------
#!/bin/bash

read -p "Give me a number: " number
if [ $number -gt 10 ];
then
  echo "Your number is greater than 10."
else
   echo "Your number is lessthan 10."
fi
-------------------------------------------------
How to check the number is odd or even:
#!/bin/bash
read -p " give me a number: " n
if [[ $( expr $n % 2 ) -eq 0 ]] 
then
   echo "your number is even number."
else
   echo "your number is odd number."
fi
-----------------------------------------------



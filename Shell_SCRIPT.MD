Shell script 

always shell script starts with  shebang --> #!/bin/bash

shebang is the first tine in shell script that we use to give the location of bash, shell sript ==bash scipt both are same.

# --> comes other than first line we use it as comment
shell script if we want to print we use command call echo

echo " Hello Shell Script"

#!/bin/bash

echo "Ramesh: Hello suresh, Good Morning"
echo " suresh: Hi Ramesh, very Good Morning"
echo "Ramesh: How are you  suresh?"
echo " suresh: I am good Ramesh, How are you"

------------
Variables is the Main  concept in all the coding or scriptting part

DRY --> Dont Repeat yourself
usually Variables we write in Captial letters, but we can use lower case too not a mandatory

VARIABLE_NAME=VALUE
$VARIABLE_NAME place a major role
eg $PERSON1
   $PERSON2

PERSON1=RAMESH
PERSON2=Suresh
-------------------
#!/bin/bash

PERSON1=Robert
PERSON2=Raheem

echo "$PERSON1: Hello $PERSON2, Good Morning"
echo "$PERSON2: Hi $PERSON1, very Good Morning"
echo "$PERSON1: How are you $PERSON2?"
echo "$PERSON2: I am good $PERSON1, How are you"
------------
Change in a single location  will effect  automatically .
we can rerodicate simple errors by using variables.
changes should not  affect

---
date command 

question: how do u run commands in shell scriot and take output?
$()
$(command)
$(date)

#!/bin/bash

DATE=$(date)
echo "date and time is $DATE"
or we can give it in flower braces
echo "date and time is: ${DATE}"


------
Arguments : args 

sh 02-variable.sh Robert John Madhan

$1=Robert
$2=John
$3=Madhan


---
we use Read command  for the secure 
read --help


read -s means what user enters wont be visible to anyone
we use read -s for not displaying crediantials

data types:
============
int, float, string, double, long, char, boolean, array, arraylist, map, set

int ---> 33,334 to 33,334
float --> 1.2 1.4
string --> ramesh
double--> 33.434454
long--> 46780987654 big big numbers we call it as long 
char --> a,b,c
boolean --> true/false  (true or false)
array --> list of persons (mad,ket,vi) array cant be change
arraylist --> same like arry but it can be changed
map --> name: mad, tech: devops  (means key value pair)
======================================
in shell dont care much about data types
----
fruits=("apple" "banana " "grapes")

============
Arrays --> we can keep multiple values , insted of storring one variable , we can store multiple, it start with zero,1,2,3..
FRUITS=("apple" "banana " "grapes")
in arrays index starts from zero 0,1,2
if we need first value we need to give 0 

echo "Frist values : ${FRUITS[0]}
echo "Second value: ${FRUITS[1]}"
echo "third  value: ${FRUITS[1]}"

variable is nothing but storage , its holding some value.
only array we use in  shell script
all fruits at a time required means , we have all notattion called "@"
07-arrays.sh
#!/bin/bash
FRUITS=("apple" "banana" "grapes")
echo "Frist values : ${FRUITS[0]}
echo "Second value: ${FRUITS[1]}"
echo "third  value: ${FRUITS[1]}"

#for all fruits we use notation called @ ; @ means all
echo "All fruits: ${FRUITS[@]}"

============
Conditions: search in good shellscript conditions

if (){
statement if expression is true
}
else{
statement if expression is false
}

in shell script  
greaterthan we rite $NUMBER -gt 100
less than we write  $NUMBER -lt 100
greater than eaqual to mean  we use $NUMBER -ge 100
less than equal to means  we use $NUMBER -le 100

if condition example :

NUMBER=$1
if [ $NUMBER -gt 100 ]
then
   echo "Given number $NUMBER is greater than 100"
else
echo "Given number $NUMBER is not greater than 100"
fi
-----
we need to make sure the spaces in between [ $NUMBER -gt 100 ]

install mysql through shell script
------------------------------------
first thing check user is root or not 
2. if root proceed, if not stop and send error, run with root user
3. not install msql
4. check installed properly
5. if success 
Then good 
not success 
show what is the error

command "id" for checking user Id check, if root user 

for normal user id,  is not zero it will be some number  (id centos -u , it will show as 1000 that means its not a root user)

for root user, id will be zero ( if we give command id -u , then it show as 0, means root user)
-------------
#!/bin/bash

ID=$(id -u)

if [ $ID -ne 0 ]
then
   echo "ERROR: please run this script with root access"
else
  echo "you are root user"
fi ## fi means reverse of if, 

yum install mysql -y
------------

sh 09-instalmsl.sh
it says error :pls run with root user
sudo sh 09-instalmsl.sh
you are a root user 

git push
git pull on the server and run the script with sudo 09-mmm

shell script : main disadvantage is , script wont stop if it see error also it will continue to run .

1.stop , clear the error and proceed (we need to follow this )
2. dont worry about error, proceed .

shell sript wont stop if it faces error.
its our responsibility  to check and proceed.
all programming  languages  will stop when error comes, but shell script wont stop if it face any error it continues  next step of execution.

EXIT status:
so EXIT status  we have it in shell script 
previous command success or not

special variable called "$?"

$? if succuss , it has zero
$? stores the previous command result succuss or failure value in exit status ($?)
succuss means 0, other wise it will have some number that means failure.
-------------
#!/bin/bash

ID=$(id -u)

if [ $ID -ne 0 ]
then
   echo "ERROR: please run this script with root access"
   exit 1 # you can give other than 0
else
  echo "you are root user"
fi ## fi means reverse of if, 

yum install mysql -y
------------







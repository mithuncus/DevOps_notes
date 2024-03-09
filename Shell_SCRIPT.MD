Shell script 

always shell script starts with #!/bin/bash

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


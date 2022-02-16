### Question 1
How many processes are currently running on your system? Use ps and wc, the first line of output of ps is not a process!
```bash
$ ps | wc -l
```
Output is `3`

### Question 2
Write a script that upon invocation shows the time and date, lists all logged-in users, and gives the system uptime. 
The script then saves this information to a logfile.
```bash
$ echo "$(date && who && uptime)" > logfile
$ cat logfile
```
Output is 
```
Tue 15 Feb 2022 02:56:56 PM EAT
icipe    :0           2022-02-15 08:42 (:0)
 14:56:56 up  6:17,  1 user,  load average: 0.19, 0.17, 0.12
```

### Question 3
Which command would you use in order to create an empty file in the current directory, let's say empty.txt?
```bash
$ touch empty.txt
```

### Question 4
You are in /home/icipe/  suppose this directory is empty. How do you create in only one command the whole path /home/icipe/Work/mini-project/RNA-Seq/?
```bash
$ mkdir -p /home/icipe/Work/mini-project/RNA-Seq/
```

### Question 5
Suppose your current working directory contains a file named seqs.txt. How do you rename this file into sequences.fasta? 
Does this have any effect on the content of the file, and if yes, what does it do?
```bash
$ mv seqs.txt sequences.fasta
```
### Question 6
How can you create in a single command a file containing the contents "Hello, world!" and named universal_greeting.txt?
```bash
$ echo "Hello world!" > universal_greeting.txt
```

### Question 7
What about creating the same file but with filename "universal greeting.txt" (the filename contains a space)?
```bash
$ echo "Hello world!" > "universal greeting.txt"
```
It will still print `Hello world!`

### Question 8
How can you use the commandline (on whichever machine you are now, that is connected to the internet) to download directly the 
file you can see on https://github.com/Fnyasimi/my-first-repo/blob/main/directory1/test.fa ? Be careful, you need to get the raw text file itself, 
not the full HTML page presenting it.
 ```bash
 $ wget https://raw.githubusercontent.com/Fnyasimi/my-first-repo/main/directory1/test.fa
 $ less test.fa
 $ q
 ```
 
### Question 9
How can you count the number of lines in this text file (test.fa)?
```bash
$ wc -l test.fa
```
The output is `10281 test.fa`

How do you count the number of sequences?
```bash
$ cat test.fa | grep -c ">"
```
or
```bash
$ grep -c ">" test.fa
```
The output is `100`


### Question 10
Extract only the identifier lines from this file, and write them into a file called "identifiers.txt".
```bash
$ grep -E ">" test.fa > identifiers.txt
$ cat identifiers.txt
```

### Question 11
How can you process the file you got from question 8 to replace all its uppercase "A" letters into lowercase "a" letters, leaving the rest untouched?
```bash
$ sed -i 's/A/a/g' test.fa
$ cat test.fa
```

### Question 12
In one command, ask for the display of all identifier lines from the same file test.fa without wrapping the lines, i.e. by having all lines displayed 
on your screen effectively start with the character '>'.
```bash
$ grep ">" test.fa
```

### Question 13
Can you write a very short script (possibly one single commandline) to extract from the same file the species names?
```bash
$ grep ">" test.fa | sed "s/PREDICTED: //g" | cut -f 2-3 -d " "
```

### Question 14
Once this is done, how do you count the species names with their order of multiplicity 
(i.e. how many sequences belong to Mus musculus, how many to Homo sapiens, etc)?
```bash
$ grep ">" test.fa | sed "s/PREDICTED: //g" | cut -f 2-3 -d " " | sort | uniq -c
```
The output is
```bash
      2 Aotus nancymaae
      1 Castor canadensis
      1 Cebus capucinus
      1 Ceratotherium simum
      6 Cercocebus atys
      5 Chinchilla lanigera
      2 Chlorocebus sabaeus
      1 Colobus angolensis
      2 Cricetulus griseus
...
```

### Question 15
Write a loop in Bash producing all the integers from 1 to 30, one per line?
```
$ for number in {1..30}
do
echo $number
done
```
or
```
$ for number in $(seq 30) ; do  echo $number ; done
```

### Question 16
Create at once 20 files called "trial1" to "trial20" and *then* rename them all by appending the suffix ".data". 
Of course, don't issue 20 commands, but just one.
```bash
$ for x in{1..20}
do
touch trial$x
mv trial$x trail$x.data
done
$ ls
```

### Question 17
Try this with the command "expr 1 / 0", whose purpose is to calculate the integer result of 1 divided by 0. What happens?
An error `expr: division by zero` occurs
Why?
The comptuter does not recognize infinity.

### Question 18
How can you separately redirect the standard output and the standard error streams into two separate files?
```bash
$ command > stdout.txt 2> stderr.txt
```

### Question 19
Write a Bash script asking "What's your name?", then waiting for you (the user) to enter you name and press Enter, 
following what the program displays some text according to the following pattern:
"Good morning/day/evening, your_name!
It's now current_time on this lovely day of current_day." and it exits.

For instance, the message written by your program would be:
```
Good day Emmanuel! It's not 12:57EAT on this lovely day of July 20. 1:00
or 'Good morning" in the morning hours, or "Good evening" in the evening hours, depending on the current time.
Of course there will be at least an if or a case construct in your script.

```
```
#!/bin/bash 
echo -n "What's your name? "
read name 
current_hour=`date +%H` 
current_time=`date "+%H:%M%Z"` 
current_day=`date "+%B %d"` 

if [[ $current_hour -lt 12 ]]
then 
    period="morning"
elif [[ $current_hour -lt 18 ]]
then 
    period="day"
else 
    period="evening"
fi 

echo "Good $period $name! It is now $current_time on this lovely day of $current_day."
```

The output is 
```
What's your name? Oronda
Good day Oronda! It is now 16:52EAT on this lovely day of February 16.
```

### Question 20
Suppose your current working directory is /home/icipe/Linux/Exercises/. What is the command that will enable to move to /home/icipe/Fun_stuff/?
```bash
$ cd ../../Fun_stuff/
```

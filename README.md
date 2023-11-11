# Hadoop Word Count Project
This project consists of a set of scripts and Java applications for running Hadoop MapReduce jobs to perform word count operations on large text datasets. The project includes two main Java applications (KC.java and RC.java) and a series of Bash scripts for compiling, running the jobs, and processing their outputs.

## Project Structure

```
.
├── KC.java                         # Java source file for KC application
├── RC.java                         # Java source file for RC application
├── nostop-output-terminal.txt      # ouput of the Java applicaiton KC     
├── stop-output-terminal.txt        # ouput of the Java applicaiton RC
├── kc.jar                          # Compiled JAR for the KC application
├──README.md
├── nostop.sh                       # Script for running the KC application
├── input                           # Input file for the Applicaions
│   ├── b1.txt
│   ├── b2.txt
│   ├── b3.txt
│   ├── b4.txt
│   └── b5.txt
├── rc.jar                          # Compiled JAR for the RC application
├── stop.sh                         # Script for running the RC application
├── top_25_KC.sh                    # Script to display top 25 words from KC output
└── top_25_RC.sh                    # Script to display top 25 words from RC output






```


## Running the MapReduce Jobs
#### Stop Words Included (RC.java)

Compile and Package the Java Application:
  
```
$ hadoop com.sun.tools.javac.Main RC.java
$ jar cf rc.jar RC*.class
$ hdfs dfs -copyToLocal /user/parallels/Wordcount/2finalstop /media/psf/SSD/dic-fi/

##Or

./stop.sh
```
## No Stop Words Included (KC.java)
 The process is similar to RC.java, using KC.java, kc.jar, and nostop.sh respectively.

 ```
 $ ./nostops.sh
 ```


## Processing the Output
To analyze the output of the MapReduce jobs, use the following scripts to display the top 25 most frequent words:

### For Stop Words Included (RC.java) Output:

```
./top_25_RC.sh
For RC.java Output:
elizabeth	691
man	527
time	485
project	442
gutenberg	435
good	431
alice	385
darcy	380
hester	361
life	359
day	347
love	338
lady	319
long	317
thought	315
eyes	310
bennet	307
letter	305
great	303
romeo	303
work	303
dear	300
mother	281
father	280
heart	278

```

### For No Stop Words Included (KC.java) Output:

```
./top_25_KC.sh
For KC.java Output:
the	17376
and	11352
of	11234
to	10022
a	6880
i	6396
in	5524
that	4377
was	4231
it	4030
her	4002
with	3428
my	3211
she	3143
you	3097
as	3079
not	3032
his	2983
he	2833
had	2830
be	2641
but	2545
for	2517
is	2130
on	1965

```
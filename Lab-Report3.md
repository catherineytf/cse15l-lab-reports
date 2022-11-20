# Lab Report 3
## find command line options 
```
tongfeiyang@Catherines-MacBook-Pro docsearch % find technical/ -empty              
technical//911report/empty.txt
```
-empty : This command finds empty dirctories and files. 

It is helpful when we need to find sepecifically empty files. 
***

```
tongfeiyang@Catherines-MacBook-Pro docsearch % find technical/ -iname "chapter-*.txt"
technical//911report/chapter-13.4.txt
technical//911report/chapter-13.5.txt
technical//911report/chapter-13.1.txt
technical//911report/chapter-13.2.txt
technical//911report/chapter-13.3.txt
technical//911report/chapter-3.txt
technical//911report/chapter-2.txt
technical//911report/chapter-1.txt
technical//911report/chapter-5.txt
technical//911report/chapter-6.txt
technical//911report/chapter-7.txt
technical//911report/chapter-9.txt
technical//911report/chapter-8.txt
technical//911report/chapter-12.txt
technical//911report/chapter-10.txt
technical//911report/chapter-11.txt
```
-iname: similar to -name. However, the match is case insensitive. 

It is helpful in looking for files with a name pattern. 
***

```
tongfeiyang@Catherines-MacBook-Pro docsearch % find technical/ -links 2
technical//plos/pmed.0020039.txt
technical//plos/pmed.0010071.txt
technical//plos/journal.pbio.0030127.txt
technical//plos/pmed.0010058.txt
technical//plos/pmed.0010070.txt
technical//plos/pmed.0010064.txt
technical//plos/pmed.0020158.txt
...
```
-links n: find files that have n links in them

It is helfful when we try to search for links in the files. 
***
## grep command line options
```
tongfeiyang@Catherines-MacBook-Pro docsearch % grep technical/ --files-with-matches *.txt  
biomed-character.txt
find-results.txt
grep-results-line.txt
grep-results.txt
plos-character.txt
plos-wordcount.txt
```
--files-with-matches: the output will show the files whose names containing selected lines. 

It can help look for files based on their names in an efficient way.
***

```
tongfeiyang@Catherines-MacBook-Pro docsearch % grep "chapter-1.txt" grep-results.txt -n
1382:technical/911report/chapter-1.txt
```
-n: It shows the line numbers of the searched files. 

Having line numbers can help us find the files more easily.
***

```
tongfeiyang@Catherines-MacBook-Pro docsearch % grep "chapter-1.txt" grep-results.txt -c
1
```
-c: count the number of lines in the output. 
It helps us to keep track of the number of selected files. 
***

## less command line options
```
tongfeiyang@Catherines-MacBook-Pro docsearch % less find-results.txt -E
...
technical/biomed/1471-2121-2-3.txt
technical/biomed/1471-213X-1-11.txt
technical/biomed/1472-684X-1-5.txt
technical/biomed/1476-4598-1-6.txt
(END) - Next: -E
```

-E: automatically exit when reaching the end of file

It is more convenient for us since we don't need to exit manually. 
***

```
tongfeiyang@Catherines-MacBook-Pro docsearch % less basepair.sh -F
grep  "base pair" $1/* > grep-results-line.txt
wc -l grep-results-line.txt
```

-F: force to open non-regular files.

It helps us to see the contents of the files. 
***

```
tongfeiyang@Catherines-MacBook-Pro docsearch % less -N grep-results.txt
1 technical/government/About_LSC/LegalServCorp_v_VelazquezSyllabus.txt
2 technical/government/About_LSC/Progress_report.txt
3 technical/government/About_LSC/Strategic_report.txt
4 technical/government/About_LSC/Comments_on_semiannual.txt
5 technical/government/About_LSC/Special_report_to_congress.txt
6 technical/government/About_LSC/CONFIG_STANDARDS.txt
7 technical/government/About_LSC/commission_report.txt
8 technical/government/About_LSC/LegalServCorp_v_VelazquezDissent.txt
9 technical/government/About_LSC/ONTARIO_LEGAL_AID_SERIES.txt
10 technical/government/About_LSC/LegalServCorp_v_VelazquezOpinion.txt
...
```
-N: display the text files with line numbers.

It gives us a better understanding of the file as well as helps us locate a specific line. 



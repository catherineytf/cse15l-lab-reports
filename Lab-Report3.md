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


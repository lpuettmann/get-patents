Download US patent grant texts from Google patents
===========================================================

The function `download_patent_files.m` goes to the bulk download page of [Google patents](http://www.google.com/googlebooks/uspto-patents-grants-text.html) and downloads the Patent Grant Full Texts. The following table shows the rough size of the files:

| Years  | Format | Size (unzipped) | 
| ------------- | ------------- | ------------- |
| 1976-2001  | `.txt` | 98 GB |
| 2002-2015  | `.XML`, `.xml` | 238 GB |

The files for 2001 are available in both formats and I choose the `.txt` format here. 

To use these codes, first define the name of the directory that will hold the files (path to data) and the start and end year, run:
```
>>parent_dname = 'patent_data';
>>year_start = 1976;
>>year_start = 2015;
```
Then to download the files from Google Patents (careful :exclamation:, these are 300 GB), run:
```
>>download_patent_files(year_start, year_end, parent_dname)
```
It puts the unzipped data files into subdirectories */[year]*. 

Then to unzip all files and delete zipped files, run:
```
>>unzip_patent_files(year_start, year_end, parent_dname)
```
Finally, in directory */1976* you should see:
```
$ls
pftaps19760106_wk01.txt
pftaps19760106_wk02.txt
pftaps19760106_wk03.txt
...
```
And in directory */2014* you should see:
```
$ls
ipg140107.xml
ipg140114.xml
ipg140121.xml
...
```

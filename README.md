# Shell Data Processing
## Powershell commands cheat sheet 
* Create a folder.
* Start a new project. Right click on that and "Open PowerShell window here as administrator".
* Create a new subfolder named shell-data-processing (or something similar)
```powershell
mkdir shell-data-processing
```
* Change directory into your subfolder. 
```powershell
cd shell-data-processing
```
* Make an empty new item named README.md
```powershell
ni README.md
```
* Make an empty new item named .gitignore
```powershell
ni .gitignore
```
* List the contents.
```powershell
ls
```
* Use curl to return the page text.
```powershell
curl "http://shakespeare.mit.edu/romeo_juliet/romeo_juliet.2.4.html"
```
* Use curl to return the page text and output to a file.
```powershell
curl "http://shakespeare.mit.edu/romeo_juliet/romeo_juliet.2.4.html" -O "data.txt"
```

#### Note: The curl command will return the source for that URL - not the displayed page contents. 

## Bash commands cheat sheet
* Open git bash in the shell-data-processing folder.
* Transform each space ' ' into a return character '\12'.Functionally, this "flat maps" each line into individual words. 
```bash
tr ' ' '\12' < data.txt
````
* Pipe the output to sort (send the results of one command as input into another command)
```bash
tr ' ' '\12' < data.txt | sort
```
* Pipe the sorted output to uniq -c to count
```bash
tr ' ' '\12' < data.txt | sort | uniq -c
```
* Pipe the reduced output to sort with -nr flag (n-numeric,r-reverse)
```bash
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr
```
* Redirect the output to results.txt
```bash
tr ' ' '\12' < data.txt | sort | uniq -c | sort -nr > results.txt
```
* Use the cat command to display the contents
```bash
cat results.txt
```
* For top 10 contents in file use
```bash
head -10 results.txt
```
* For least 2 contents use
```bash
tail -2 results.txt
```
### Similary in powershell
PowerShell cat:
```powershell
Get-Content results.txt
gc results.txt -head 2
gc results.txt -tail 2
```
### Bash up arrow: - 
The commands which we enter previously will display on screen. It helps us to not to type complete command again.

## Important Bash commands (>, >>, |, cat)

* Bash redirect (>):  type ls > results.txt to redirect the contents of your directory into a file. 
* Bash redirect & append (>>): use two arrows to append rather than overwrite. 
* Type ls to list the contents of the default directory. Send the result to a new file called temp.txt (ls > temp.txt). 
* Copy in Bash is not CTRL+C as in Windows, instead use CTRL+SHIFT+C.


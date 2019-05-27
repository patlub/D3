| Command | What it does                                                                                                                                                                                                                           | example usage                                                                                                                                                                                                                              |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| find    | Carries out command on each file that find matches                                                                                                                                                                                     | find . -name "*.pyc" -type f -delete# Delete all files with                                                                                                                                                                                |
| xargs   | A filter for feeding arguments to a command,  and also a tool for assembling the commands themselves.  In a place where command substitution fails with a too many  arguments error, substituting xargs often works                    | find users.txt -type f | xargs grep "patrick" # search the file users.txt if found ls | xargs -n 8 echo lists the files in  the current directory in 8 columns. grep -rliwZ GUI / | xargs -0 rm -f  Will remove any files containing “GUI” |
| expr    | All purpose expression evaluator.  Concatenates and evaluates the arguments according to the operation given (Arguments are separated by spaces).  Operations may be arithmetic, comparison, string, or logic                          | expr 4+2 returns 6 expr 12 \* 3 returns 36  The multiplication operator must be  escaped when used in an arithmetic  expression with expr                                                                                                  |
| sed     | This is a non-interactive stream editor.  It receives text input, whether from stdin or from a file,  performs certain operations on specified lines of the input,  one line at a time, then outputs the result to stdout or to a file | sed -e '/^$/d' $filenameThe -e option is an edit instruction,-n option tells sed to print only those lines matching the pattern.                                                                                                           |
| awk     | This a text processing language                                                                                                                                                                                                        | [Link](https://www.tldp.org/LDP/abs/html/awk.html) to the documentation on Awk.                                                                                                                                                            |


Other commands include:

1. rm -rf
2. mv
3. copy
4. grep
5. man # the systems’s manual pager
6. kill # terminate a given program/process
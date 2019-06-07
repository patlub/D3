| Command | What it does                                                                                                                                                                                                                           | example usage                                                                                                                                                                                                                              |
|---------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| find    | used to find files and folders                                                                                                                                                                                     | find /dir/path/look/up -name "dir-name-here"                                                                                                                                                                                |
| xargs   | A filter for feeding arguments to a command,  and also a tool for assembling the commands themselves.                       | echo 'one two three' xargs mkdir
| expr    | All purpose expression evaluator.  Concatenates and evaluates the arguments according to the operation given (Arguments are separated by spaces).  Operations may be arithmetic, comparison, string, or logic                          | expr 4 \+ 2 returns 6 expr 12 \* 3 returns 36  The operator must be  escaped when used in an arithmetic  expression with expr                                                                                                  |
| sed     | This is a non-interactive stream editor.  It receives text input, whether from stdin or from a file,  performs certain operations on specified lines of the input,  one line at a time, then outputs the result to stdout or to a file | $sed 's/unix/linux/' geekfile.txt                                                                                                           |
| awk     | This a text processing language                                                                                                                                                                                                        | [Link](https://www.tldp.org/LDP/abs/html/awk.html) to the documentation on Awk.                                                                                                                                                            |


Other commands include:

1. rm -rf
2. mv
3. copy
4. grep
5. man # the systems’s manual pager
6. kill # terminate a given program/process

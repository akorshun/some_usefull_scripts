# some_usefull_scripts

## Show all *.c files in current directory and subdirectories with ' \' at the end of each file
    find -name "*.c" -print | cut -c 3- | sed -e 's/$/ \\/'
    
## Show all *.c headers in current directory with ';' at the end of each file
    cat *.c | sed -ne '/void/p' -ne '/int/p' -ne '/char/p' -ne '/size_t/p' | sed -ne '/(/p' | sed '/return/d' | sed '/malloc/d' | sed '/\[/d' | uniq | sed 's/$/;/'

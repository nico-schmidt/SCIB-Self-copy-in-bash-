# SCIB (Self copy in bash)

SCIB is a Bash script that attaches itself onto an executable file.

SCIB intercepts the execution of the target executable file.

SCIB attaches itself at the beginning of an executable file. When the file is executed, SCIB first executes an action (in the examples it prints a message), and then the executable file will be executed normally.

SCIB is just a proof of concept to show an easy way to inject code onto an existing executable.


Some examples:

With a script:

    $ ./myScript.sh
    Hello, I'm the script!
    
    $ ./SCIB.sh myScript.sh   # Executing SCIB with the target script
    
    $ ./myScript.sh   # Executing the script again, this time the execution was intercepted by SCIB
    Hello! SCIB is here! :)
    Hello, I'm the script!


With a C program:

    $ ./myCProgram one two three
    Hello, I'm the C program! I've been called with 3 parameters
    one
    two
    three
    
    $ ./SCIB.sh myCProgram  # Executing SCIB with the target program
    
    $ ./myCProgram one two three  # Executing the program again, this time the execution was intercepted by SCIB
    Hello! SCIB is here! :)
    Hello, I'm the C program! I've been called with 3 parameters
    one
    two
    three
    

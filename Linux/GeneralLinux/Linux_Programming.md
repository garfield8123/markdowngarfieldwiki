# linux programming

## Common GCC Options

| Option | Meaning |
| --- | --- |
| -ansi | Supports only ANSI-standard C syntax (This option disables some GNU C-specific features, such as the \_\_asm\_\_\ and \_\_type\_\_\ of keywords) when used with g++, supports only ISO standard C++ |
| -c | Compiles and generates only the object file |
| -DMACRO | Defines the macro with the string "1" as its value |
| -DMACRO=DEFN | Defines the macro as DEFN, where DEFN is some text string |
| -E | Runs only the C preprocessor |
| -fallow-single-precision | Performs all math operations in single precision |
| -fpcc-struct-return | Returns all struct and union values in memory, rather than in registers (Returning values this way is less efficient, but at least its compatible with other compilers) |
| -fPIC | Generates position-independent Code (PIC) suitable for use in a shared library |
| -freg-struct-return | When possible, returns struct and union values registers |
| -g | Generates debugging information (The GNU debugger can use this information) |
| -I DIRECTORY | Searches the specified directory for files that you include by using the #include preprocessor directive |
| -L DIRECTORY | Searches the specified directory for libraries |
| -l LIBRARY | Searches the specified library when linking |
| -o FILE | Generates the specified output file (used to designate the name of an executable file) |
| -00 (two zeros) | Doesn't optimize |
| -O or -O1 (letter O) | Opitmizes the generated code |
| -O2 | Optimizes more than those done for -O |
| -O3 | Performs optimizations even eyond those done for -O2 |
| -Os | Opitmizes the size (to reduce the total amount of code) |
| -pedantic | Generates errors if any non-ANSI-standard exntensions are used |
| -pg | Adds extra code to the program so that, when run, this program generates information that the gprof program can use to display timing details for various parts of the program |
| -shared | Generates a shared object file (typically used to create a shared library) |
| -UMACRO | Undefines the specified macros |
| -v | Displays the GCC version number |
| -w | Doesn't generate warning messages |
| -w1, OPTIOn | Passes the OPTION string (containing multiple comma-separated options) to the linker. To create a shared library named libxxx.so.1, for example, use the following flag: w1,-soname,libXXX.so.1 |

## Predefined variables in GNU Make

| Variable | Meaning |
| --- | --- |
| $% | Member name for targets that are archives. If the target is libDisp.a (image.o), $% is image.o |
| $\* | Name of the target file without the extension |
| $+ | Names of all dependent files with duplicate dependencies, listed in their order of occurrence |
| $< | The name of the first dependent file |
| $? | names of all dependent files (with spaces between the names) that are newer than the target |
| $@ | Complete name of the target. if the target is liDisp.a (image.o) for example $@ is libDisp.a |
| $^ | Names of all dependent files, with spaces between the names. Duplicates are removed from the dependent filenames |
| AR | Name of archive-maintaining program (default value: ar) |
| ARFLAGS | Flags for the archive-maintaining program (default value: rv) |
| AS | Name of the assembler program that converts the assembly langauge to oject code (default value: as) |
| ASFLAGS | Flags for the assembler |
| CC | Name of the C compiler (default value: cc) |
| CFLAGS | Flags that are passed to the C compiler |
| CO | Name of the program that extracts a file from RCS (default value: co) |
| COFLAGS | Flags for the RCS co program |
| CPP | Name of the C preprocessor (default value: $(CC) -E) |
| CPPFLAGS | Flags for the C Preprocessor |
| CXX | Name of the C++ Compilier (Default value: g++) |
| CXXFLAGS | Flags that are passed to the C++ Compilier |
| FC | Name of the FORTRAN compiler (default value: f77) |
| FFLAGS | Flags for the FORTRAN compilier |
| LDFLAGS | Flags for the compilier when its supposed to invoke the linker ld |
| RM | Name of the command to delete a file (default value rm -f) |

## GNU Make Options

| Option | Meaning |
| --- | --- |
| -b | ignores the variable given but accepts that variable for compatibility with other version of make |
| -C DIR | Changes to the specified directory before reading the makefile |
| -d | prints debugging information |
| -e | Allows environment variables to override definitions of similarly named variables in the makefile |
| -f FILE | Reads FILE as the makefile |
| -h | Displays the list of make options |
| -i | Ignores all errors in commands executed when building a target |
| -I DIR | Searches the specified directory for included makefiles (The capability to include a file in a makefile is unique to GNU make) |
| -j NUM | Specifies the number of jobs that make can run simulatenously |
| -k | Continues to build unrelated targets, even if an error occurs when building one of the targets |
| -l LOAD | Doesn't start a new job if load average is at least LOAD (A floating point number) |
| -m | Ignores the variable given but accepts that variable for compatibility with other versions of make |
| -n | Prints the commands to execute but does not execute them |
| -o FILE | Does not rebuild the file named FILE, even if it is older than its dependents |
| -p | Displays the make database of variables and implicit rules |
| -q | Does not run anything but returns 0 (zero) if all targets are up to date. 1 if anything needs updating, or if an error occurs |
| -r | gets rid of all built-in rules |
| -R | Gets rid of all built-in variables and rules |
| -s | Works silently (Without displaying the commands as they execute) |
| -t | Changes the time stamp of the files |
| -v | Displays the version number of make, icensing information, and a copyright notice |
| -w | Displyas the name of the working directory before and after processing the makefile |
| -w FILE | Assumes that the specified file ahs been modified (used wit -n to see what happens if you modify that file) |

## Common GDB Commangs

| Command | what it does |
| --- | --- |
| break NUM | Sets a breakpoint at the specified line number, NUM |
| bt | Displays a trace of all stack frames (Shows you the sequence of function calls so far) |
| clear FILENAME:NUM | Deletes the breakpoint at a specific line number, NUM, in the source file FILENAME |
| continue | continues running the pogram being debugged |
| display EXPR | Displays the value of an expression, EXPR (consisting of variables defined in the program) each time the program stops |
| file FILE | loads the specified executable file FILE, for debugging |
| help NAME | Displays help on the command named NAME |
| info break | Displays a list of current breakpoints, including information on how many times each breakpoint is reached |
| info files | Displays detailed information about the file being debugged |
| info func | Displays all function names |
| info local | Displays information about local variables of the current function |
| info prog | Displays the execution status of the program being debugged |
| info var | Displays all global and static variable names |
| kill | Ends the program you're debugging |
| list | lists a section of the source code |
| make | Runs the make utility to rebuild the executiable without leaving gdb |
| next | Advanced one line of source code in the current function without stepping into other functions |
| print EXPR | Shows the value of the expression EXPR |
| quit | Quits gdb |
| run | Starts running the currently loaded executable |
| set variable VAR=VALUE | Sets the value fo teh variable VAR to VALUE |
| shell CMD | Executes the shell command CMD without leaving gdb |
| step | Advanced one line in the current function, stepping into other functions if any |
| watch VAR | Shows the value of the variable named VAR whenever the value changes |
| where | Displays the call sequence. Use this command to locate where your program died |
| x/F ADDR | Examines the contents of the memory location at address ADDR in the format specified by the letter F, which can be o (octal), x(hex), d (decimal), u (unsigned decimal), t (binary), f (float), a (address), i (instruction), c (char), or s (string). You can append a letter, indicating the size of data type to the format letter. Size letter are b (byte), h (halfworld, 2bytes), w(word, 4 bytes), and g (giant, 8 bytes). ADDR is the name of a variable or pointer |

## /etc/init.d autorun program

* copy script to /etc/init.d with #!/bin/bash to ensure it runs the bash program

```
chkconfig --add myscript
chkconfig --level 2345 myscript on
chkconfig --list | grep myscript

```

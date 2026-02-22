# Linux shell scripting

## Built in commands in bash

| Function | Description |
| --- | --- |
| .filename [arguments] | Reads and executes commands from the specified filename using the optional arguments (like source command) |
| : [arguments] | Expands the arguemnts but doesn't process them |
| [expr] | Evaluates the expression expr and returns zero status if expr is true |
| alias [name[=value]..] | Allows one value to equal another. You could set xyz to run bg |
| bg [job] | Puts the specified job in the background. If no job is specified, it puts the currently executing command in the background |
| break [n] | Exits from a for, while, or until loop. If n is specified, the nth enclosing loop is exited |
| cd [dir] | Changes the current directory to dir |
| command [-pVv] cmd [arg ..] | Runs teh command cmd with the specified arguemnts (ignoring any shell function named cmd) |
| continue [n] | Starts the next iteration of the for, while, or until loop. If n is specified, the next iteration of the nth enclosing loop is started |
| declare [-frxi] [name[=value]] | Declares a variable with the specified name and optionally assigns it a value |
| dirs [-l] [+/-n] | Displays the list of currently remembered directories |
| echo [-neE] [arg ...] | Displays the arguments, arg ..., on standard output |
| enable [-n] [-all] | Enables or disables the specified built-in commands |
| eval [arg....] | Concatentates the arguements, arg .., and executes them as a command |
| exec [command [arguments]] | Replaces the current instance of the shell with a new process that runs the specified command with the given arguments |
| exit [n] | Exits the shell with the status code n |
| export [-nf] [name[=word]] | Defines a specified environment variable and exports it to future processes |
| fc -s [pat=rep] [cmd] | Re-executes the command after replacing the pattern pat with rep |
| fg [jobspec] | Puts the specified job, jobspec, in the foreground. If no job is specified, it puts the most recent job in the foreground |
| hash [-r] [name] | Remembers the full pathname of a specified command |
| help [cmd] | Displays help information for specified built-in commands |
| history [n] | DIsplays past commands or past n commands, if you specify a number n |
| jobs [-lnp] [jobspec] | Lists currently active jobs |
| kill [-s sigspec -sigspec] [pid jobspec] | Ends the process specified |
| let arg [arg ...] | Evaluates each argument and returns 1 if the last arg is 0 |
| local [name[=value]...] | Creates a local variable with the specified name and value (used in shell functions) |
| logout | exists a login shell |
| popd [+/-n] | Removes the specified number of entries from the directory stack |
| pushd [dir] | Adds a specified directory,dir, to the top of the directory stack |
| pwd | Prints the full pathname of the current working directory |
| read [-r] [name ...] | Reads a line from standard input and parses it |
| readonly [-f] [name ...] | Marks the specified variables as read-only so that the variables can't be changed later |
| return [n] | Exists the shell function with teh return value n |
| set [--abefhkmnptuvxldCHP] [-o option] [arg ...] | Sets various flags |
| shift [n] | Makes the n+1 argument $1, the n+2 argument $2, and .. |
| times | Prints the accumulated user and system times from processes run from the shell |
| trap [-l] [cmd] [sigpsec] | Executes cmd when the signal sigspec is received |
| type [-all] [-type -path] name [name ..] | Indicates how the shell interprets each name |
| ulimit [-SHacdfmstpnuv [limit]] | Controls resources available to the shell |
| umask [-S] [mode] | Sets the file creation mask -- the default permission to the mode specified for the files |
| unalias [-a] [name ...] | undefines a specified alias |
| unset [-fv] [name ..] | Removes the definition of specified variables |
| wait [n] | Waits for a specified process (n represents PID) to terminate |
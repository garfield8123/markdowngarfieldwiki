# Database Servers

* Different database
* [PostgreSQL](#postgresql)
* [MySQL](#mysql)
* [MongoDB](#mongodb)

## PostgreSQL

PostgreSQL known for its advanced database features. Follows the standard atomicity, consistency, isolation, and durability (ACID) guidlines used by commericial database and supports many fancy features

### Install PostgreSQL

```
sudo apt install postgresql
systemctl status postgresql

sudo dnf install postgresql-server
systemctl enable postgresql
su -c '/usr/bin/postgresql-setup' --initdb

```

### PostgreSQL Command line paramters

| short Name | Long Name | Description |
| --- | --- | --- |
| -a | --echo-all | Displays all SQL lines processed from a script file in the output |
| -A | --no-align | Sets the output format to unaligned mode, with data not didsplayed as a formatted table |
| -c | --command | Executes the specified SQL statement and exits |
| -d | -dbname | Specifies the database to connect with |
| -e | --echo-queries | Echoes all queries to the screen |
| -E | --echo-hidden | Echoes all hidden psql meta-commands to the screen |
| -f | --file | Exeuctes SQL commands from the specified file and exits |
| -F | --field-separator | Specifies the character used to separate column data when in unaligned mode (with the default being a comma) |
| -h | --host | Specifies the IP address or hostname of the remote PostgreSQL server |
| -H | --html | HTML table output mode |
| -l | --list | Displays a list of available databases on the server and exits |
| -L | --log-file | Sends a session log to a file |
| -n | --no-readline | Disables enhanced command-line editing |
| -o | --output | Redirects query output to the specified file |
| -p | --port | Specifies the PostgreSQL server TCP port to connect with |
| -P | --pset | Sets the table printing option specified to a specified value |
| -q | --quiet | Quiet mode; doesn't display output messages |
| -R | --record-sperator | Uses the specified character as the record sparator (with the default being the newline character) |
| -s | --single-step | Prompts to continue or cancel after every SQL query |
| -S | --single-line | Specifies that the Enter key defines the end of a SQL query instead of a semicolon |
| -t | --tuples-only | Disables column headers and footers in table output |
| -U | --username | Uses the specified username to connect to the PostgreSQL server |
| -v | --variable | Sets the specified variable to a specified value |
| -V | --version | Displays the psql version number and exits |
| -W | --password | Forces a password prompt |
| -x | --expanded | Enables expanded table output to display additional information for records |
| -X | --nopsqlrc | Doesn't process the psql startup file |
| -z | --field-separator-zero | Sets the field separator to zero bytes |
| -? | --help | Displays the psql command line help and exits |

### Postgresql commands

| Shortcut | Description |
| --- | --- |
| \l | Lists all available databases |
| \c | connect to database |
| \dt | list the tables in the database |
| \du | list postgresql users |
| \z | List table privileges |
| \? | List all vailable meta commands |
| \h | list all avilable SQL commands |
| \q | Exit the database |

```
sudo --login -u postgres
psql

CREATE DATABASE name;
\l
\c name

```

### Create user

```
CREATE ROLE rich LOGIN;

```

## MySQL

Fastest storage engine and de facto for web applications

## MariaDB

Having a commerical database company in charge of an opensource database project scared many people in the open-source community intro

### Install Mariadb

```
sudo apt install mariadb-server
systemctl status mariadb

sudo dnf install mariadb-server
systemctl enable mariadb

```

### Mysql command-line parameters

| Short Parameter | Long Parameter | Description |
| --- | --- | --- |
| -? | --help | Displays help information |
|  | --abort-source-on-error | Aborts source operations in case of errors |
|  | --auto-rehash | Enables automatic rehashing |
| -A | --no-auto-rehash | Disables automatic rehashing |
| -b | --no-beep | Disables beep on errors |
| -B | --batch | Doesn't use a history file |
|  | --binary-as-hex | Prints binary data as hex |
|  | --character-sets-dir=name | Displays column type information |
|  | --column-type-info | Displays column type information |
| -c | --comments | Preserves comments |
| -C | --compress | Compresses all information sent between the client and the server |
| -a | --debug | Runs a non-debug version, catches any errors, and exits |
|  | --debug-check | Checks memory and opens file usage at exit |
| -T | --debug-info | Displays debug information at exit |
| -D | --database=name | Specifies the database to use |
| -e | --execute=name | Executes the specified statement and exits |
| -E | --vertical | Displays query output vertically, one data field per line |
| -f | --force | Continues if a SQL error occurs |
| -G | --named-commands | Enables named mysql commands |
| -h | --host=name | Specifies the MariaDB server hostname (the default is localhost) |
| -H | --html | Displays query output in HTML code |
| -I | --ignore-spaces | Ignores spaces after function names |
|  | --init-command=name | SQL coommand to execute when connecting to the server |
|  | --line-numbers | Displays line numbers for errors |
|  | --local-infile | Enables/disables the LOAD DATa LOCAL INFILE feature |
| -L | --skip-line-numbers | Doesn't display line numbers for errors |
| -n | --unbuffered | Flushes the buffer after each query |
| -N | --skip-column-names | Doesn't display column names in results |
| -o | --one-database | ignores statements except those for one default database named on the command line |
|  | --pager | Uses pager to display results |
| -p | --password | Prompts for the password for the user account |
| -P | --port=# | Specifies the TCP port number to use for the network connection |
|  | --progress-reports | Gets progress reports for long-running commands |
|  | --prompt=name | Sets the command-line prompt |
|  | --protocol=name | Sets the protocol to use for the connection (tcp, socket, or pipe) |
| -q | --quick | Doesn't cache each query result |
| -r | --raw | Displays column values without escape conversion |
|  | --reconnect | Reconnects if the connection is lost |
| -s | --silent | Uses silent mode |
| -S | --socket=name | Specifies a socket for connection to the localhost |
|  | --ssl | Enables SSL for the connection |
| -t | --tale | Displays output in table form |
|  | --tee=name | Appends output to the specified file |
| -u | --user=name | Specifies the user account to log in as |
| -U | --safe-updates | Allows only UPDATE and DELETE statements that specify key values |
| -v | --verose | Uses Verbose mode |
| -w | --wait | If the connection can't be established, waits and retries |
| -X | --xml | Displays query output in XHTML code |

### Mysql Commands

| Command | Shortcut | Description |
| --- | --- | --- |
| ? | \? | Accesses help |
| clear | \c | Clears the command |
| connect | \r | Connects to the database and server |
| delimiter | \d | Sets a SQL statement delimiter |
| edit | \e | Edits the command with the command-line editor |
| ego | \G | Sends the command to the MariaDB server and displays the results vertically |
| exit | \q | Exits from the mysql program |
| go | \g | Sends the command to the MariaDB server |
| help | \h | Displays help |
| nopager | \n | Disables the output pager and sends the output to STDOUT |
| notee | \t | Doesn't send output to the output file |
| pager | \P | Sets the pager command to the specified program (used more as default) |
| print | \p | Prints the current command |
| prompt | \R | Changes the mysql command prompt |
| quit | \q | Quits from the mysql program (same as exit) |
| rehash | # | Rebuilds the command completion hash table |
| source | \ . | Executes the SQL script in the specified file |
| status | \s | Retrieves status information from the MariaDB server |
| system | ! | Executes a shell command on the system |
| tee | \T | Appends all output to the specified file |
| use | \u | Uses another database |
| charset | \C | Changes to another character set |
| warnings | \W | Shows warnings after every statement |
| nowarning | \w | Doens't show warnings after every statement |

```
SHOW DATABSES;
SHOW TABLES;
CREATE DATABASE name;
USE name;
SHOW TABLES;

```

### MYSQL Users

```
GRANT SELECT,INSERT,DELETE,UPDATE ON test.* TO rich IDENTIFIED BY 'test';

```

## MongoDB

NoSQL doesn't create tables but instead stores data as invididual documents. Stores data as individual JSON elements making each data document indepdent of the others
# Mail Servers

Different mailservers

* [Mail Servers](#mail-servers)
* [Mail Transfer Agents (MTA)](#mail-transfer-agents-mta)
  + [sendmail](#sendmail)
  + [Configuration file location](#configuration-file-location)
    - [M4 Macro processor](#m4-macro-processor)
  + [Macro meaning](#macro-meaning)
  + [Syntax of sendmail.cf](#syntax-of-sendmailcf)
  + [Other sendmail directories](#other-sendmail-directories)
  + [.forward file](#forward-file)
  + [Alias file /etc/alias](#alias-file-etcalias)
  + [postfix](#postfix)
  + [Installing Postfix](#installing-postfix)
  + [Exim](#exim)
* [Mail Delivery Agent (MDA)](#mail-delivery-agent-mda)
  + [Binmail](#binmail)
  + [Procmail](#procmail)
* [Test mail](#test-mail)

## Mail Transfer Agents (MTA)

Different Mail Transfer Agents (MTA) Packages

### sendmail

MTA package gained popularity by being extremely versatile. Virtual domains, message forwarding, user aliases, mail lists, and host masquerading. Large configuration file

#### Configuration file location

* /etc/mail/sendmail.cf -> Fedora
* /etc/sendmail.cf -> OpenSUSE
* Opensuse -> /etc/sysconfig/sendmail (YaST Control Center) (mail transfer agent)

##### M4 Macro processor

generates the sendmail.cf configuration file

* sendmail.mc, generic\_linux.mc, linux.mc

```
dn1 #######################################################
dn1 # File: ex.m4
dn1 # A simple M4 extension
dn1 ######################################################
define('hello', 'Dear sir/Mdadmen)dn1
define('bye',
'sincercely,
customer service')dn1
dn1 Now type the letter and use the macros
hello,
This is to inform you that we received your recent inquiry.
We will respond to your question soon.
bye

```

```
m4 ex.m4

```

* /etc/mail/sendmail.mc
* /usr/share/sendmail-cf -> Fedora
* /usr/share/sendmail -> OpenSuse
* uses mc extension, but is same as macro

```
m4 /etc/mail/sendmail.mc > /etc/mail/sendmail.cf

```

#### Macro meaning

| macro | meaning |
| --- | --- |
| VERSIONID ('setup for linux') | macro inserts the version information enclosed in quotes into the output |
| OSTYPE('linux') | Specifies Linux as the OS. Have t specify this macro early to ensure proepr configruation |
| MAILER(smtp) | Describes the mailer. Accoridng to nstructions in the /usr/share/sendmail-cf/README file. MAILER delcarations are always placed at the end of the sendmail.mc file, and MAILER (smtp) always precedes MAILER (procmail). The mailer smtp refers to the SMTP mailer |
| FEATURE | Macros request various speciail features. FEATURE ('blacklist\_recipents'), for example turns on the capability to block incoming mail for certain usernames, hosts, or addresses. The specification of what mail to allow or refuse is placed in the access database |
| MASQUERADE\_AS('mydomain.com') | Causes sendmail to label outgoing mail as having come from the host mydomain.com. The idea is for a large organization to setup a single sendmail server that handles the mail for many subdomains and makes everything appear to come from a single domain. |
| MASQUERADE\_DOMAIN(subdomain.mydomain.com) | Instructs sendmail to send mail from an address such as user@subdomain .com as having originated from the same username as the domain specified by the MASQUERADE\_AS macro |

#### Syntax of sendmail.cf

| Operator | Description |
| --- | --- |
| C | Defines a class, a variable (think of it as a set) that can cotain several values. Cwlocalhost adds the name localhost to the class w |
| D | Defines a macro, a name associated with a single value. DnMAILER-DAEMON defines the macro n as MAILER-DAEMON |
| F | Defines a class that's been read from a file. FW /etc/mail/local-host-names reads the names of hosts from the file /etc/mail/local-host-names and adds them to the class w |
| H | Defines the format of header lines that sendmail inserts into a message. H?P?Return-Path:<$g> defines the Return-Path: field of the header |
| K | Defines a map (a key-value pari database). Karith arith defines the map named arith as the compiled in map of the name |
| M | Specifies a mailer. The following lines define the procmail mailer:Mprocmial, P=/usr/bin/procmail,F=DFMPhnu9,S=EnvFromSMTP/HdrFromSMTP,R=EnvToSMTP/HdrFromSMTP,T=DNS/RFC822/X-Unix,A=procmail -Y -m $h $f $u |
| O | Assigns a value to an option. O AliasFile=/etc/aliases defines the AlisasFile option to /etc/aliases, which is the name of the sendmail alias file |
| P | Defines values for the precedence field. P junk=-100 sets to -100 the precedence of messages marked with the hader field Precedence: junk |
| R | Defines a rule (A rule has left side and right side, if input matches the left side, the right side replaces it. This rule is called rewriting rule) R$\* ; $1 strips trailing semicolons |
| S | Labels a ruleset you can start defining with subsequent R control lines. Scanonify=3 labels the next ruleset as canonify and ruleset 3 |
| T | Adds a username to the trusted (class t) Troot adds root to the class of trusted users |
| V | Defines the major version number of the configuration file |

#### Other sendmail directories

| Directory | Description |
| --- | --- |
| /etc/mail/access | names or IP addresses or both of hosts allowed to send mail (usedful in stopping spam (unwanted email)) |
| /etc/mail/access.db | Access database generated from the /etc/mail/access file |
| /etc/mail/helpfile | Help information for SMTP commands |
| /etc/mail/local-host-names | Names by which this host is known |
| /etc/mail/mailertable | Mailer table used to voerride how mail is routed (The entry comcast.net smtp:smtp.comcast.net has too be sent to smtp.comcast.net) |
| /etc/mail/relay-domains | Hosts that permit relaying |
| /etc/mail/trusted-users | List of users allowed to send mail using other users' names without a warning |
| /etc/mail/userdb.db | User database file contianing information about each user's login name and real name |
| /etc/mail/virtusertable | Database of suers with virtual-domain addresses hosted on this system |

```
makemap hash /etc/mail/mailertable < /etc/mail/mailertable
cd /etc/mail
make

```

#### .forward file

```
[email protected], wilbur\

```

#### Alias file /etc/alias

Mailing list creation

```
brown: glbrown
all: jessica, isaac, alex, caleb, glbrown

```

```
sendmail -bi

```

### postfix

Modular application using several different programs to implement MTA. Simple, just 2 small configuration files with plaintext parameters and value names to define functionality

#### Installing Postfix

* No configuraition -> Leaves the default postfix configuration files
* Internet site -> Sets postfix to send & receive email messages directly on the internet
* Internet with smarthost -> Sets postfix to forward all outbound messages to a specific host, but receive incoming mail delivery
* Satellite system -> Sets postfix to route all mail to a remote smarthost server
* Local only -> Processes only mail destined for local user accounts on the system

```
sudo apt install postfix

sudo dnf install psotfix

sudo systemctl enable postfix
sudo systemctl start postfix

sudo firewall-cmd --add-service=smtp --permanent
sudo firewall-cmd --reload

```

* /etc/postfix/main.cf to store email server settings

### Exim

One large program to handle all functions. Attempts to avoid queuing messages as much as possible instead relying on immediate deliverly

## Mail Delivery Agent (MDA)

Different Mail Delivery Agents (MDA) Packages

### Binmail

Most popular MDA program. Located in the system, /bin/mail. became popular due to its simplicity. Read email messages stored in the standard /var/spool/mail

### Procmail

Comes from its versatility in creating user-configured recipes that allow a user to direct how the server processes received mail. A user can create a personal .procmailrc file in their $HOME directory to direct messages. Does mail stuff automatically.

## Test mail

```
sudo apt-get install mailutils

sudo dnf install mailx

mail rich
mail

```
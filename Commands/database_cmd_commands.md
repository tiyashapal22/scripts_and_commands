# Database Cmd Commands

**Note** : The Database Commands must be run under SQLPlus. 
| Query                                       | Command                               |   Example                              |
|:--------------------------------------------|:--------------------------------------|---------------------------------------:|
| To Check if the pluggable Database is Mounted or Not  | Select name, open_mode from v$pdbs;   |                                        |
| To Open/Start Pluggable Database            | Alter Pluggable database <name> open; | Alter Pluggable database orclpdb open; |
| To start the main database                  | Startup                               |                                        |
| To Stop the main Database                   | Shutdown                              |                                        |

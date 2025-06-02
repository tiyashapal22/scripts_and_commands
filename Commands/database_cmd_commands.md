# Database Cmd Commands

## To be run with SQLPlus
 
| Query                                       | Command                              |   Example                              |
|:--------------------------------------------|:--------------------------------------|---------------------------------------:|
| To Start SQLPlus | sqlplus / as sysdba |       |
| Checking for Pluggable Database| show pdbs|   |
| To Check if the pluggable Database is Mounted or Not  | Select name, open_mode from v$pdbs;   |                                        |
| To Open/Start Pluggable Database Manually     | Alter Pluggable database {name} open; | Alter Pluggable database orclpdb open; |
| To set Pluggable Database auto startup (after started manually first)      | Alter Pluggable database {name} save state; | Alter Pluggable database orclpdb save state; |
| To start the main database                    | Startup                               |                                        |
| To Stop the main Database                     | Shutdown                              |                                        |

## To be run directly in CMD

| Query                                       | Command                              |   Example                              |
|:--------------------------------------------|:--------------------------------------|---------------------------------------:|
|Start Listner| lsnrctl start| |
|Stop Listner| lsnrctl stop| |
|Listner status| lsnrctl status| |
|Check TNS Connection | tnsping {TNS Namespace}| tnsping ORCL |

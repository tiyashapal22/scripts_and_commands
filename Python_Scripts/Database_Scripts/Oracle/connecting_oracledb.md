# Connecting Oracle DataBase

## Code

```Python
import cx_Oracle

try:
    # create  connection1
    conn1 = cx_Oracle.connect('system/root@//localhost:1521/XE')
except Exception as ex:
    print("Error occurs while creating the connection1", ex)
finally:
    conn1.close()
        
```
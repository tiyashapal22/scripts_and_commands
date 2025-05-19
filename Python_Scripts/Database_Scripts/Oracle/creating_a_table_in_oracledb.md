# Creating a table in Oracle Database

## Code

```Python
import cx_Oracle

try:
    # create  connection1
    conn1 = cx_Oracle.connect('system/root@//localhost:1521/XE')
except Exception as ex:
    print("Error occurs while creating the connection1", ex)
else:
    print(conn1.version)
    try:
        # create cursor1
        cur1 = conn1.cursor()
        sql_query1 = """
               create table placement_details
               (First_Name varchar(50),
               Last_Name varchar(50),
               Company varchar(50),
               Age number)
              """
        cur1.execute(sql_query1)
    except Exception as ex:
        print("Error occurs while execute the 1st query",ex)
    else:
        print("First Table created successfully")
        conn1.commit()
    finally:
        cur1.close()
finally:
    conn1.close()
```
# tigerSql
### tigerSql is a wrapper for Python's `sqlite3` module.
tigerSql allows you to interface with `sqlite3` and store dictionaries and lists along with the standard strings, integers, and floats. 

## Demo
```
import tigerSqlite
db = tigerSqlite.Sqlite('testingdb.db')
db.insert('testing_table', *[('name', {'first':'James', 'last':'Petullo'}), ('id', 40000), ('age', 18)])
current_info = db.get_name_age('testing_table')
print(current_info)
```
## Results:
```
[({'first':'James', 'last':'Petullo'}, 17)]
```

## Table management and creation

TigerSqlite supports custom table creation with raw type wrappers:

```
from tigerSqlite import Roar, ParseLog

class MyTable(Roar, ParseLog):
    __tablename__ = 'MYTABLE'
    __filename__ = 'mytable.db'
    def __init__(self):
        self.name = tigerSqliteTypeString(1)
        self.age = tigerSqliteTypeInt(2)
        self.timestamp = tigerSqliteTypeDefaultTimeStamp(3)
        
 if __name__ == "__main__":
     MyTable().create_table()
   
```
When run, a database file `mytable.db` will be created with a table named `MYTABLE` with columns `name, age, timestamp`.

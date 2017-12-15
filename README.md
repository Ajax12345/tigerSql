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

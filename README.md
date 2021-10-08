Python SQL
==========

### Python SQL Result to Dictionary 
```
con = sqlite3.connect(BACKUP_DIR)
cur = con.cursor()

sql = '''SELECT * FROM student'''
cur.execute(sql)
desc = cur.description
column_names = [col[0] for col in desc]
data = [dict(zip(column_names, row)) for row in cur.fetchall()]

for row in data:
    print(row)

con.close()
```

### SQLite3 Date Base 
```
SELECT * FROM weather WHERE dt1 >= date('now', '-1', 'days') AND dt1 < date('now');
```

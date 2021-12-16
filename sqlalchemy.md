# [sqlalchemy](https://www.sqlalchemy.org/) - The Python SQL Toolkit and Object Relational Mapper

## get list of columns from sqlalchemy model

```python
def get_column_names(model):
    columns = [col.name for col in model.__table__.columns]
    return columns
```

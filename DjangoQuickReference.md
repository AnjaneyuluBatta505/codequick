# Django Quick Reference
## UML Diagrams of Generic Views
http://epydoc.pythondiary.com/generic-views/

## class based views 
https://ccbv.co.uk/

## django github repo
https://github.com/django/django/tree/master/django


## proxy models with extra fields & non related foreignkey relationship

```python
from django.db import models
from abc.models import Model1
from abc.models import Model2

class Model(object):
    '''
    Skip extra field validation "models.E017"
    '''

    @classmethod
    def _check_model(cls):
        errors = []
        return errors

class ModelCls(Model, Model1):
    fk = models.ForeignKey(
            Model2,
            db_column='column_name',
            to_field='field_name',
            null=True,
            on_delete=models.SET_NULL,
            db_constraint=False,
            related_name='+')

    class Meta:
        proxy = True
        app_label='app_name'

```

### profiler middleware to improve the django app performance

```python
import cProfile, pstats, io
from django.utils.deprecation import MiddlewareMixin

class ProfilerMiddleware(MiddlewareMixin):
	def process_request(self, request):
		pr = cProfile.Profile()
		pr.enable()
		request._pr = pr

	def process_response(self, request, response):
		request._pr.disable()
		s = io.StringIO()
		sortby = 'cumulative'
		# Sort the output by cumulative time it took in fuctions/methods.
		ps = pstats.Stats(request._pr, stream=s).sort_stats(sortby)
		# Print only 100 most time consuming functions
		ps.print_stats(100)
		print(s.getvalue())
		return response
```

### get executed sql queries with execution times

```python
from django.db import connection
print(connection.queries)
```


### list all models in django project with table and columns
```python
from importlib import import_module
from django.apps import apps
from django.conf import settings

def get_column_list_from_model(model):
    return [field.column for field in model._meta.fields]

def get_all_models_in_project():
    models = apps.get_models()
    # django.contrib.auth.models.Permission
    for model in models:
        table_name = model._meta.db_table
        table_columns = get_column_list_from_model(model)
        order = ",".join(table_columns)
        print(f"{table_name}: {order}")
```

### get all parent tables of a model

```python
from django.db.models.fields.related import OneToOneField, ForeignKey
def get_parent_tables(model):
    fields = model._meta.get_fields()
    parent_tables = set()
    related_fields = [
        OneToOneField,
        ForeignKey
    ]
    for field in fields:
        if field.__class__ in related_fields:
            related_model = field.related_model
            tbl = related_model._meta.db_table
            parent_tables.add(tbl)
            parent_tables.update(get_parent_tables(related_model))
    return parent_tables
```

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

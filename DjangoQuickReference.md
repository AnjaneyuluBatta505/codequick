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

class EasyPostLabel(Model, Model1):
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

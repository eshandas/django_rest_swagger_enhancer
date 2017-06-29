# Django Rest Swagger Enhancer
Some enhances on Django Rest Swagger

## Version

0.0.2

## Features

* Adds a textarea for POST, PUT and PATCH methods in Django Rest Swagger.
* Can add text boxes for query parameters.

## Dependencies

* Django 1.11
* Django Rest Framework 2.1.2
* Django Rest Swagger 3.6.3

## Installation

* Using pip

```
pip install django_rest_swagger_enhancer
```

## Setup

* In urls.py, add an endpoint for Swagger like the following and you should start seeing textareas in POST, PUT and PATCH:

```
from django_rest_swagger_enhancer.schema_generator import get_swagger_view, CustomSchemaGenerator


schema_view = get_swagger_view(title='My Django Project', generator_class=CustomSchemaGenerator)


urlpatterns = [
    ...
    url(r'^swagger/$', schema_view),
    ...
]
```

* For query strings, text boxes can be added by adding **query_params** variable in your **APIView**

```
class GetAllAPI(APIView):
    ...
    query_params = [
        {'name': 'query_string_1', 'required': True},
        {'name': 'query_string_2', 'required': False}]

    def get(self, request):
        ...

    def post(self, request):
        ...
```

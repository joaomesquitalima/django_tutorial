# django_tutorial
Possui uma ajuda pra mexer com django
<h1>Passo 1: Instalar Django</h1>

```bash
pip install Django
```
<h1>Passo 2: Iniciando um projeto</h1>
<p>1. Va na pasta e por meio do prompt digite o comando: </p>

```bash
django-admin startproject mysite
```

<h1>Passo 3: Rode o projeto</h1>
<p>1. Va na pasta e por meio do prompt digite o comando: </p>

```bash
python manage.py runserver
```
<h1>Crie um aplicativo</h1>
<p>1. Crie uma pasta da pagina</p>

```bash
python manage.py startapp pagina
```

<p>2. Crie uma visualização</p>
<ol>Vá na pasta criada e procure por views.py, escreva isso no arquivo</ol>

```bash
from django.shortcuts import render
from django.http import HttpResponse
# Create your views here.

def index(request):
    return HttpResponse('Minha primeira pagina com django')
```

<p>3. Na pasta da pagina crie um arquivo urls.py e escreva isso: </p>

```bash
from django.urls import path

from . import views

urlpatterns = [
    path('',views.index,name="index"),
]
```
<p>4. Va na pasta da pagina principal e no arquivo urls.py deixe assim:</p>

```bash
from django.contrib import admin
from django.urls import include, path

urlpatterns = [
    path('pools/',include('pagina.urls')),
    path('admin/', admin.site.urls),
]
```


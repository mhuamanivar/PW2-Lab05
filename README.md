<div align="center">
  <table width="1000px">
    <theader>
      <tr>
        <td><img src="https://github.com/rescobedoq/pw2/blob/main/epis.png?raw=true" alt="EPIS" style="width:50%; height:auto"/></td>
        <th>
          <span style="font-weight:bold;">UNIVERSIDAD NACIONAL DE SAN AGUSTIN</span><br />
          <span style="font-weight:bold;">FACULTAD DE INGENIERÍA DE PRODUCCIÓN Y SERVICIOS</span><br />
          <span style="font-weight:bold;">DEPARTAMENTO ACADÉMICO DE INGENIERÍA DE SISTEMAS E INFORMÁTICA</span><br />
          <span style="font-weight:bold;">ESCUELA PROFESIONAL DE INGENIERÍA DE SISTEMAS</span>
        </th>
        <td><img src="https://github.com/rescobedoq/pw2/blob/main/abet.png?raw=true" alt="ABET" style="width:50%; height:auto"/></td>
      </tr>
    </theader>
    <tbody>
      <tr><td colspan="3"><span style="font-weight:bold;">Formato</span>: Guía de Práctica de Laboratorio</td></tr>
      <tr><td><span style="font-weight:bold;">Aprobación</span>:  2022/03/01</td><td><span style="font-weight:bold;">Código</span>: GUIA-PRLD-001</td><td><span style="font-weight:bold;">Página</span>: 1</td></tr>
    </tbody>
  </table>
</div>

<div align="center">
    <span style="font-weight:bold;">INFORME DE LABORATORIO</span><br />
</div>

<div align="center">
  <table width="1000px">
    <theader>
      <tr><th colspan="6">INFORMACIÓN BÁSICA</th></tr>
    </theader>
    <tbody>
      <tr><td>ASIGNATURA:</td><td colspan="5">Programación Web 02</td></tr>
      <tr><td>TÍTULO DE LA PRÁCTICA:</td><td colspan="5">Django</td></tr>
      <tr><td>NÚMERO DE PRÁCTICA:</td><td>05</td><td>AÑO LECTIVO:</td><td>2023 A</td><td>NRO. SEMESTRE:</td><td width="60px">  III  </td></tr>
      <tr><td>FECHA DE PRESENTACIÓN:</td><td>20/06/2023</td><td>HORA DE PRESENTACIÓN:</td><td colspan="3">23:59</td></tr>
      <tr>
        <td colspan="4">NOMBRE:
          <ul>
            <li>Melsy Melany Huamaní Vargas</li>
          </ul>
        </td>
        <td>NOTA:</td><td></td>
      </tr>
      <tr>
        <td colspan="6" width="1000px">DOCENTES:
          <ul>
            <li>Anibal Sardon Paniagua</li>
          </ul>
        </td>
      </tr>
    </tbody>
  </table>
</div>


##
## SOLUCIÓN Y RESULTADOS

<br/>

**INSTALACIÓN PARA EL USO DE PYTHON Y DJANGO**

Se utiliza el sistema Windows para usar las herramientas necesarias para crear los proyectos.<br/><br/>

- Creando el ambiente y activandolo.
    ```sh
    C:\Users\melsy\Lab05>mkdir my_env
    C:\Users\melsy\Lab05>cd my_env
    C:\Users\melsy\Lab05\my_env>python -m venv C:\Users\melsy\Lab05\my_env
    C:\Users\melsy\Lab05\my_env>Scripts\activate.bat
    (my_env) C:\Users\melsy\Lab05\my_env>
    ```
    <br/>

- Actualizando el pip de python.
    ```sh
    (my_env) C:\Users\melsy\Lab05\my_env>python.exe -m pip install --upgrade pip
    Requirement already satisfied: pip in c:\users\melsy\lab05\my_env\lib\site-packages (22.3.1)
    Collecting pip
      Using cached pip-23.1.2-py3-none-any.whl (2.1 MB)
    Installing collected packages: pip
      Attempting uninstall: pip
        Found existing installation: pip 22.3.1
        Uninstalling pip-22.3.1:
          Successfully uninstalled pip-22.3.1
    Successfully installed pip-23.1.2
    ```
    <br/>

- Instalando Django con pip.
    ```sh
    (my_env) C:\Users\melsy\Lab05\my_env>pip install Django
    Collecting Django
      Using cached Django-4.2.2-py3-none-any.whl (8.0 MB)
    Collecting asgiref<4,>=3.6.0 (from Django)
      Using cached asgiref-3.7.2-py3-none-any.whl (24 kB)
    Collecting sqlparse>=0.3.1 (from Django)
      Using cached sqlparse-0.4.4-py3-none-any.whl (41 kB)
    Collecting tzdata (from Django)
      Using cached tzdata-2023.3-py2.py3-none-any.whl (341 kB)
    Installing collected packages: tzdata, sqlparse, asgiref, Django
    Successfully installed Django-4.2.2 asgiref-3.7.2 sqlparse-0.4.4 tzdata-2023.3
    ```
    <br/>

- Mostrando los paquetes instalados con ``pip list``.
    ```sh
    (my_env) C:\Users\melsy\Lab05\my_env>pip list
    Package    Version
    ---------- -------
    asgiref    3.7.2
    Django     4.2.2
    pip        23.1.2
    setuptools 65.5.0
    sqlparse   0.4.4
    tzdata     2023.3
    ```
    <br/>




##
**I. EJERCICIO: LIBRARY**

Se utiliza el sistema Windows para usar las herramientas necesarias para crear los proyectos.<br/><br/>

***Creating a skeleton website***

- Creación del proyecto library en la carpeta Scripts.

    ```sh
    (my_env) C:\Users\melsy\Lab05\my_env>cd Scripts
    (my_env) C:\Users\melsy\Lab05\my_env\Scripts>django-admin startproject library
    ```
    <br/>

- Creación de la aplicación catalog.

    ```sh
    (my_env) C:\Users\melsy\Lab05\my_env\Scripts>cd library
    (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py startapp catalog
    ```
    <br/>

- Registro de la aplicación catalog dentro del archivo settings.py.

    ```py
    # Application definition

    INSTALLED_APPS = [
        'django.contrib.admin',
        'django.contrib.auth',
        'django.contrib.contenttypes',
        'django.contrib.sessions',
        'django.contrib.messages',
        'django.contrib.staticfiles',
        'catalog.apps.CatalogConfig',
    ]
    ```
    <br/>

- Especificación de la base de datos dentro del archivo settings.py, no se necesita hacer cambios.

    ```py
    # Database
    # https://docs.djangoproject.com/en/4.2/ref/settings/#databases

    DATABASES = {
        'default': {
            'ENGINE': 'django.db.backends.sqlite3',
            'NAME': BASE_DIR / 'db.sqlite3',
        }
    }
    ```
    <br/>
  
- Otros ajustes del proyecto: TimeZone dentro del archivo settings.py.

    ```py
    # Internationalization
    # https://docs.djangoproject.com/en/4.2/topics/i18n/

    LANGUAGE_CODE = 'en-us'

    TIME_ZONE = 'America/Lima'

    USE_I18N = True

    USE_TZ = True
    ```
    <br/>

- Conectar el URL mapper dentro del archivo urls.py.

    - Se añade estas líneas al final del archivo para agregar un nuevo elemento a la lista ``urlpatterns``, que incluye un oath para redirigir peticiones con patrón ``catalog/`` al módulo ``catalog.urls``.

      ```py
      # Use include() to add paths from the catalog application
      from django.urls import include

      urlpatterns += [
          path('catalog/', include('catalog.urls')),
      ]
      ```
      <br/>

    - Ahora añadimos estas líneas nuevamente al final para redireccionar la URL raíz ``127.0.0.1:8000`` al URL ``127.0.0.1:8000/catalog/``.

      ```py
      #Add URL maps to redirect the base URL to our application
      from django.views.generic import RedirectView
      urlpatterns += [
          path('', RedirectView.as_view(url='catalog/', permanent=True)),
      ]
      ```
      <br/>

    - También añadimos estas líneas para habilitar el servicio de archivos estáticos.

      ```py
      # Use static() to add URL mapping to serve static files during development (only)
      from django.conf import settings
      from django.conf.urls.static import static

      urlpatterns += static(settings.STATIC_URL, document_root=settings.STATIC_ROOT)
      ```
      <br/>

- Crear archivo urls.py en carpeta catalog para definir la ``urlpatterns`` importada colocando las siguientes líneas.

    ```py
    from django.urls import path
    from . import views

    urlpatterns = [

    ]
    ```
    <br/>

- Prueba del framework del sitio web.

    - Ejecutamos las migrations de la base de datos

      ```sh
      (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py makemigrations
      No changes detected
      (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py migrate
      Operations to perform:
        Apply all migrations: admin, auth, contenttypes, sessions
      Running migrations:
        Applying contenttypes.0001_initial... OK
        Applying auth.0001_initial... OK
        Applying admin.0001_initial... OK
        Applying admin.0002_logentry_remove_auto_add... OK
        Applying admin.0003_logentry_add_action_flag_choices... OK
        Applying contenttypes.0002_remove_content_type_name... OK
        Applying auth.0002_alter_permission_name_max_length... OK
        Applying auth.0003_alter_user_email_max_length... OK
        Applying auth.0004_alter_user_username_opts... OK
        Applying auth.0005_alter_user_last_login_null... OK
        Applying auth.0006_require_contenttypes_0002... OK
        Applying auth.0007_alter_validators_add_error_messages... OK
        Applying auth.0008_alter_user_username_max_length... OK
        Applying auth.0009_alter_user_last_name_max_length... OK
        Applying auth.0010_alter_group_name_max_length... OK
        Applying auth.0011_update_proxy_permissions... OK
        Applying auth.0012_alter_user_first_name_max_length... OK
        Applying sessions.0001_initial... OK
      ```
      <br/>

    - Corremos el servidor (modificar)

      ```sh
      (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py runserver
      Watching for file changes with StatReloader
      Performing system checks...

      System check identified no issues (0 silenced).
      June 19, 2023 - 20:46:06
      Django version 4.2.2, using settings 'library.settings'
      Starting development server at http://127.0.0.1:8000/
      Quit the server with CTRL-BREAK.

      [19/Jun/2023 20:46:17] "GET / HTTP/1.1" 301 0
      Not Found: /catalog/
      [19/Jun/2023 20:46:17] "GET /catalog/ HTTP/1.1" 404 2329
      Not Found: /favicon.ico
      [19/Jun/2023 20:46:18] "GET /favicon.ico HTTP/1.1" 404 2446
      [19/Jun/2023 20:46:35] "GET / HTTP/1.1" 301 0
      Not Found: /catalog/
      [19/Jun/2023 20:46:35] "GET /catalog/ HTTP/1.1" 404 2329
      Not Found: /favicon.ico
      [19/Jun/2023 20:46:35] "GET /favicon.ico HTTP/1.1" 404 2446
      ```
      <br/>

- (Desafío: Observar lo sucedido) En la url ``http://127.0.0.1:8000`` se puede ver la salida correctamente, debido a que aun no hay páginas definidas en el módulo ``catalog.urls``. Además, se ve que aunque hayamos ingresado a ese link, con la configuración anterior y el mapeo de URLs, este se redirige automáticamente a ``http://127.0.0.1:8000/catalog/``.

    <img src="img" style="width:70%"/><br/>
    <br/>

***Using models***

- Definiendo los modelos del Library.

    - Modelo Genre, se crea la clase ``Genre`` que representa un género literario.

      ```py
      class Genre(models.Model):
          name = models.CharField(max_length=200, help_text='Enter a book genre (e.g. Science Fiction)')

          def __str__(self):
              return self.name
      ```
      <br/>

    - Modelo Book, se aumenta el import ``reverse`` con ``from django.urls import reverse`` y la clase ``Book`` que representa un libro, pero no un libro específico.

      ```py
      class Book(models.Model):
          title = models.CharField(max_length=200)

          # Foreign Key used because book can only have one author, but authors can have multiple books
          # Author is a string rather than an object because it hasn't been declared yet in the file
          author = models.ForeignKey('Author', on_delete=models.SET_NULL, null=True)

          summary = models.TextField(max_length=1000, help_text='Enter a brief description of the book')
          isbn = models.CharField('ISBN', max_length=13, unique=True,
                                  help_text='13 Character <a href="https://www.isbn-international.org/content/what-isbn">ISBN number</a>')

          # ManyToManyField used because genre can contain many books. Books can cover many genres.
          # Genre class has already been defined so we can specify the object above.
          genre = models.ManyToManyField(Genre, help_text='Select a genre for this book')

          def __str__(self):
              return self.title

          def get_absolute_url(self):
              # Returns the URL to access a detail record for this book.
              return reverse('book-detail', args=[str(self.id)])
      ```
      <br/>

    - Modelo BookInstance, se importa ``uuid`` con ``import uuid`` para las instancias únicas de los libros y se crea la clase ``BookInstance`` que representa una copia específica de un libro.

      ```py
      class BookInstance(models.Model):

          id = models.UUIDField(primary_key=True, default=uuid.uuid4, help_text='Unique ID for this particular book across whole library')
          book = models.ForeignKey('Book', on_delete=models.RESTRICT, null=True)
          imprint = models.CharField(max_length=200)
          due_back = models.DateField(null=True, blank=True)

          LOAN_STATUS = (
              ('m', 'Maintenance'),
              ('o', 'On loan'),
              ('a', 'Available'),
              ('r', 'Reserved'),
          )

          status = models.CharField(
              max_length=1,
              choices=LOAN_STATUS,
              blank=True,
              default='m',
              help_text='Book availability',
          )

          class Meta:
              ordering = ['due_back']

          def __str__(self):
              return f'{self.id} ({self.book.title})'
      ```
      <br/>

    - Modelo Author, se crea la clase ``Author`` que representa a un autor de libros.

      ```py
      class Author(models.Model):
          
          first_name = models.CharField(max_length=100)
          last_name = models.CharField(max_length=100)
          date_of_birth = models.DateField(null=True, blank=True)
          date_of_death = models.DateField('Died', null=True, blank=True)

          class Meta:
              ordering = ['last_name', 'first_name']

          def get_absolute_url(self):
              # Returns the URL to access a particular author instance.
              return reverse('author-detail', args=[str(self.id)])

          def __str__(self):
              return f'{self.last_name}, {self.first_name}'
      ```
      <br/>

- Reiniciando y ejecutando las migraciones a base de datos.
    ```sh
    (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py makemigrations
    Migrations for 'catalog':
      catalog\migrations\0001_initial.py
        - Create model Author
        - Create model Book
        - Create model Genre
        - Create model BookInstance
        - Add field genre to book

    (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py migrate
    Operations to perform:
      Apply all migrations: admin, auth, catalog, contenttypes, sessions
    Running migrations:
      Applying catalog.0001_initial... OK
    ```
    <br/>

- (Desafío: Crear modelo Languague) Se crea la clase ``Language`` para que tenga un campo en caso de tener un libro en otro idioma.
    ```py
    class Language(models.Model):

        name = models.CharField(max_length=200,
                                help_text="Enter the book's natural language (e.g. English, French, Japanese etc.)")

        def __str__(self):
            return self.name
    ```
    <br/>

    - Se hacen nuevamente las migraciones a base de datos.

      ```sh
      (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py makemigrations
      Migrations for 'catalog':
        catalog\migrations\0002_language.py
          - Create model Language

      (my_env) C:\Users\melsy\Lab05\my_env\Scripts\library>python manage.py migrate
      Operations to perform:
        Apply all migrations: admin, auth, catalog, contenttypes, sessions
      Running migrations:
        Applying catalog.0002_language... OK
      ```
      <br/>




##
## COMMITS MÁS IMPORTANTES

<br/>

<img src="commits" style="width:70%"/><br/><br/>

##
## CUESTIONARIO

- **Resalte un aprendizaje que adquiri ́o al momento de estudiar Django.**

  respuesta

<br/>
<br/>

##
## REFERENCIAS

- https://developer.mozilla.org/en-US/docs/Learn/Server-side/Django/Tutorial_local_library_website
- https://github.com/mdn/django-locallibrary-tutorial
- https://github.com/rescobedoq/pw2/tree/main/labs/lab05

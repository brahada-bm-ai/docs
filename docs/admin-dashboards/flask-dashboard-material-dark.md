title: Flask Dashboard Material Dark

# [Flask Dashboard Material Dark](https://appseed.us/admin-dashboards/flask-dashboard-material-dark)

**Open-Source Admin Dashboard** coded in **[Flask Framework](https://palletsprojects.com/p/flask/)** on top of **Material Dark Dashboard** design (free version) - Provided by **AppSeed** [Web App Generator](https://appseed.us/app-generator).

<br />

## Dashboard Features
---

- SQLite, PostgreSQL, SQLAlchemy ORM
- Alembic (DB schema migrations)
- Modular design with **Blueprints**
- Session-Based authentication (via **flask_login**)
- Forms validation
- Deployment scripts: Docker, Gunicorn / Nginx
- UI Kit: **[Material Dark Dashboard](https://flask-dashboard-material-dark.appseed.us/login)** (Free version) provided by **Creative-Tim**
- **MIT License**
- Support: Free support via **Github** and (Paid) **24/7 LIVE Support** via [Discord](https://discord.gg/fZC6hup)

<br />

## Dashboard Links
---

- [Flask Dashboard Material Dark](https://appseed.us/admin-dashboards/flask-dashboard-material-dark) - Product page
- [Flask Dashboard Material Dark](https://github.com/app-generator/flask-dashboard-material-dark) - Source code (published on Github)
- [Flask Dashboard Material Dark](https://flask-dashboard-material-dark.appseed.us/login) - LIVE demo

<br />

![Flask Dashboard Material Dark - Open-Source Admin Panel](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-material-dark-screen.png)

<br />

## Prepare your environment
---

The product is built on top of [Flask](https://palletsprojects.com/p/flask/), a popular Python Web Framework. To build the app, Python3 should be installed properly in the workstation. If you are not sure if Python is properly installed, please open a terminal and type `python --version`. The full-list with dependencies and tools required to build the app:

- [Python3](https://www.python.org/) - the programming language used to code the app
- [Git](https://git-scm.com/) - used to clone the source code from the Github repository
- A [Github](https://github.com/) account - the invitation to the source code, will be sent on your account.
- Basic development tools (g++ compiler, python development libraries ..etc) used by Python to compile the app dependencies in your environment.

<br />

> Check Python (using the terminal)

```bash
$ # Check Python version
$ python --version
Python 3.7.2 # <--- All good
```

<br />

> Check GIT command tool (using the terminal)

```bash
$ # Check git
$ git --version
$ git version 2.10.1.windows.1 # <--- All good
```

<br />

For more information on how to set up your environment please access the resources listed below. In case we've missed something, contact us on Discord.

- [How to set up Python](/how-to/install-python)
- [Setup CentOS for development](/how-to/setup-centos-for-development/)
- [Setup Ubuntu for development](/how-to/setup-ubuntu-for-development/)
- [Setup Windows for development](/how-to/setup-windows-for-development/)

<br />

## Project Structure
---

The boilerplate code is built with a modular structure that follows the recommended pattern used by many open-source projects. The most important files and  directories are shown below:

<br />

```bash
< PROJECT ROOT >                          # application root folder
    |
    |--- app/__init__.py                  # application constructor  
    |--- app/base/                        # base blueprint
    |--- app/base/static/assets           # Img, CSS, Janascript files
    |--- app/base/templates               # Jinja2 files (layouts, login pages)
    |                |---<errors>         # Dir - Error pages: 404, 500
    |                |---<login>          # Dir - Login and Registration pages
    |                |---<site_template>  # Dir - Components: footer, sidebar, header
    |
    |
    |--- app/home/                        # home blueprint
    |--- app/home/templates               # Jinja2 files (Pages): index, icons, tables
    |                |---- index.html     # Main dashboard page
    |                |---- maps.html      # Maps page
    |                |---- profile.html   # Profile Page
    |                |---- tables.html    # UI Tables
    |                |---- icons.html     # Ui Icons
    |
    |--- .env                             # store env variables
    |--- config.py                        # app configuration profiles: Debug, Production
    |
    |--- requirements.txt                 # Requirements for development - SQLite storage
    |--- requirements-pgsql.txt           # Requirements for production  - Pgsql Database
    |
    |--- run.py                           # bootstrap the app
    |
    |-----------------------------
```

<br />

## Build from sources
---

```bash
$ # Get the code
$ git clone https://github.com/app-generator/flask-material-dashboard.git
$ cd flask-material-dashboard
$
$ # Virtualenv modules installation (Unix based systems)
$ virtualenv --no-site-packages env
$ source env/bin/activate
$
$ # Virtualenv modules installation (Windows based systems)
$ # virtualenv --no-site-packages env
$ # .\env\Scripts\activate
$
$ # Install modules - SQLite Database
$ pip3 install -r requirements.txt
$
$ # OR with PostgreSQL connector
$ # pip install -r requirements-pgsql.txt
$
$ # Set the FLASK_APP environment variable
$ (Unix/Mac) export FLASK_APP=run.py
$ (Windows) set FLASK_APP=run.py
$ (Powershell) $env:FLASK_APP = ".\run.py"
$
$ # Set up the DEBUG environment
$ # (Unix/Mac) export FLASK_ENV=development
$ # (Windows) set FLASK_ENV=development
$ # (Powershell) $env:FLASK_ENV = "development"
$
$ # Start the application (development mode)
$ # --host=0.0.0.0 - expose the app on all network interfaces (default 127.0.0.1)
$ # --port=5000    - specify the app port (default 5000)  
$ flask run --host=0.0.0.0 --port=5000
$
$ # Access the dashboard in browser: http://127.0.0.1:5000/
```

<br />

## Deployment

The app is provided with a basic configuration to be executed in [Docker](https://www.docker.com/), [Gunicorn](https://gunicorn.org/), and [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/).

<br />

### [Docker](https://www.docker.com/) execution
---

The application can be easily executed in a docker container. The steps:

> Get the code

```bash
$ git clone https://github.com/app-generator/flask-material-dashboard.git
$ cd flask-material-dashboard
```

> Start the app in Docker

```bash
$ sudo docker-compose pull && sudo docker-compose build && sudo docker-compose up -d
```

Visit `http://localhost:5005` in your browser. The app should be up & running.

<br />

### [Gunicorn](https://gunicorn.org/)
---

Gunicorn 'Green Unicorn' is a Python WSGI HTTP Server for UNIX.

> Install using pip

```bash
$ pip install gunicorn
```
> Start the app using `gunicorn` binary

```bash
$ gunicorn --bind 0.0.0.0:8001 run:app
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.


<br />

### [Waitress](https://docs.pylonsproject.org/projects/waitress/en/stable/)
---

Waitress (Gunicorn equivalent for Windows) is meant to be a production-quality pure-Python WSGI server with very acceptable performance. It has no dependencies except ones that live in the Python standard library.

> Install using pip

```bash
$ pip install waitress
```
> Start the app using [waitress-serve](https://docs.pylonsproject.org/projects/waitress/en/stable/runner.html)

```bash
$ waitress-serve --port=8001 run:app
Serving on http://localhost:8001
```

Visit `http://localhost:8001` in your browser. The app should be up & running.

<br />

## Flask Dashboard Material Dark - App Screens
---

<br />

![Flask Dashboard Material Dark - UI Fonts Page.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-material-dark-screen-1.png)

<br />

![Flask Dashboard Material Dark - Google Maps Page.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-material-dark-screen-2.png)

<br />

![Flask Dashboard Material Dark - User Profile Page.](https://raw.githubusercontent.com/app-generator/static/master/products/flask-dashboard-material-dark-screen-3.png)

<br />

## Credits & Links
---

<br />

## What is [Flask](https://www.palletsprojects.com/p/flask/)

[Flask](https://www.palletsprojects.com/p/flask/) is a lightweight WSGI web application framework. It is designed to make getting started quick and easy, with the ability to scale up to complex applications. It began as a simple wrapper around Werkzeug and Jinja and has become one of the most popular Python web application frameworks.

<br />

## [What is dashboard](https://en.wikipedia.org/wiki/Dashboard_(business))

In information technology, a **[dashboard](https://en.wikipedia.org/wiki/Dashboard_(business))** is a user interface that, somewhat resembling an automobile's dashboard, organizes and presents information in a way that is easy to read. However, a computer dashboard is more likely to be interactive than an automobile dashboard (unless it is also computer-based). To some extent, most graphical user interfaces (GUIs) resemble a dashboard - by [Techtarget](https://searchcio.techtarget.com/definition/dashboard)

<br />

## [Material Dashboard Dark](https://www.creative-tim.com/product/material-dashboard-dark)

Material Dashboard Dark Edition is a free Material Bootstrap 4 Admin with a fresh, new design inspired by Google's Material Design. Material Dashboard is a free Material Bootstrap 4 Admin with a fresh, new design inspired by Google's Material Design - provided by Creative-Tim.

<br />

---
[Flask Dashboard Material Dark](https://appseed.us/admin-dashboards/flask-dashboard-material-dark) - Provided by **AppSeed** [Web App Generator](https://appseed.us/app-generator).
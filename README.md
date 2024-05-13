<div align="center">
    <a href="https://appseed.us/product/rocket-pro/django/">
        <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/51070104/272178364-cbac6d97-b2dc-4d95-bab6-891f4ee7d84d.png"" width="64" height="64" alt="Rocket Icon">
    </a>
    <h1>
        <a href="https://appseed.us/product/rocket-pro/django/">
            Rocket Django PRO
        </a>
    </h1>
    <p>
        <strong>TailwindCSS</strong> &bull; <strong>Flowbite</strong> &bull; <strong>API (DRF)</strong> &bull; <strong>Celery Beat</strong> &bull; <strong>DataTables</strong> &bull; <strong>Charts</strong> &bull; <strong>Docker</strong> &bull; <strong>CI/CD</strong>
    </p>  
    <h3>
        <a href="https://docs.appseed.us/products/rocket/django/">
           📖 Docs
        </a>
        &nbsp; &bull; &nbsp;        
        <a href="https://rocket-django-pro.onrender.com/">
            Demo
        </a>
        &nbsp; &bull; &nbsp; 
        <a href="https://appseed.us/support/">
            Support 🚀
        </a>
    </h3>    
</div>

<br />

<div align="center">
    <img src="https://github-production-user-asset-6210df.s3.amazonaws.com/51070104/272299949-6f4a8fd7-7cce-472a-9566-9519db338c7d.gif" alt="Django Rocket - Open-source Starter styled with Tailwind and Flowbite.">
</div>

<br />

## Why [Rocket Django PRO](https://appseed.us/product/rocket-pro/django/)

#### ***Supercharge your app instantly, launch faster, make $***

Login users, process payments and send emails at lightspeed. Spend your time building your startup, not integrating APIs. **Rocket Django** provides you with the boilerplate code you need to launch, FAST. 

#### ***Rocket your startup in days, not weeks*** 

The Django boilerplate with all you need to build your SaaS, AI tool, or any other web app. From idea to production in 5 minutes.

#### **48+ hours of headaches**

 - 1 hrs to setup the project 
 - 2 hrs integrate tooling
 - 2 hrs to handle Stripe
 - 1 hrs for Docker
 - 1 hr Google Oauth
 - ∞ hrs overthinking...
 - Free [Support](https://appseed.us/support/) via `Email` & [Discord](https://discord.gg/fZC6hup) 

<br />

## Start in `Docker`

> 👉 Unzip sources or clone the private repository (requires a [purchase](https://appseed.us/product/rocket-pro/django/))

```bash
$ unzip rocket-django-pro.zip
// OR
$ git clone https://github.com/app-generator/priv-rocket-django-pro.git
$ cd rocket-django-pro
```

<br />

> Start the APP in `Docker`

```bash
# Optional (kill all existing containers)
$ docker container kill $(docker ps -q) ; docker container rm $(docker ps -a -q) ; docker network prune -f 
# Start the APP
$ docker-compose up --build 
```

Visit `http://localhost:5085` in your browser. The app should be up & running. The starter comes with two default users:

- Ordinary user: `test` / `test@appseed.us` / `Pass12__` (the password)
- Django SuperUser (admin): `admin` / `admin@appseed.us` / `Pass12__` (the password)

Once authenticated with the above credentials, the sidebar shows different items. 

<br />

## Manual Build 

> 👉 Unzip sources or clone the private repository (requires a [purchase](https://appseed.us/product/rocket-pro/django/))

```bash
$ unzip rocket-django-pro.zip
// OR
$ git clone https://github.com/app-generator/priv-rocket-django-pro.git
$ cd rocket-django-pro
```

> 👉 Edit `.env` using `env.sample` or keep the default values

```env
DEBUG=True

SECRET_KEY=<STRONG_KEY_HERE>

...
```

> 👉 Install **Django** modules via `VENV`  

```bash
$ virtualenv env
$ source env/bin/activate
$ pip install -r requirements.txt
```

> 👉 Install **Tailwind/Flowbite** (separate terminal)

> **Node Version**: `v18.20.0` or above

```bash
$ npm install
$ npm run dev
$ npx tailwindcss -i ./static/assets/style.css -o ./static/dist/css/output.css --watch
```

> 👉 Migrate DB

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

> 👉 `Create Superuser` & Start the APP

```bash
$ python manage.py createsuperuser # create the admin
$ python manage.py runserver       # start the project
```

<br />

## Use MySql 

By default, the starter uses SQLite for persistence. In order to use MySql, here are the steps: 

- Start the MySql Server
- Create a new DataBase
- Create a new user with full privilegies over the database 
- Install the MySql Python Driver (used by Django to connect)
  - `$ pip install mysqlclient`
- Edit the `.env` with the SQL Driver Information & DB Credentials 

```env

DB_ENGINE=mysql
DB_HOST=localhost
DB_NAME=<DB_NAME_HERE>
DB_USERNAME=<DB_USER_HERE>
DB_PASS=<DB_PASS_HERE>
DB_PORT=3306

```

Once the above settings are done, run the migration & cretae tables: 

```bash
$ python manage.py makemigrations
$ python manage.py migrate
```

<br />

## Production Build

To use the starter in production mode, here are the steps: 

- Set  **DEBUG=False** in `.env`
- Execute `collectstatic` command
  - `$ python manage.py collectstatic --no-input`

As a model, feel free to take a look at [build.sh](./build.sh), the file executed by the CI/CD flow for Render:   


<br />

## **Deploy on Render**

- Create a Blueprint instance
  - Go to https://dashboard.render.com/blueprints this link.
- Click `New Blueprint Instance` button.
- Connect your `repo` which you want to deploy.
- Fill the `Service Group Name` and click on the `Update Existing Resources` button.
- Edit the Environment and [specify the PYTHON_VERSION](https://render.com/docs/python-version)
  - Version `3.11.5` was used for **[this deployment](https://rocket-django.onrender.com/)**
- After that, your deployment will start automatically.

At this point, the product should be LIVE.

<br />

## Codebase 

```bash
< PROJECT ROOT >
   |
   |-- core/                 # Project Settings 
   |    |-- settings.py 
   |    |-- wsgi.py     
   |    |-- urls.py     
   |
   |-- home/                 # Presentation app 
   |    |-- views.py         # serve the HOMEpage  
   |    |-- urls.py     
   |    |-- models.py
   |
   |-- apps/                 # Utility Apps 
   |    |-- common/          # defines models & helpers
   |    |    |-- models.py   
   |    |    |-- util.py 
   |    |-- users            # Handles Authentication 
   |    |-- api              # DRF managed API
   |    |-- charts           # Showcase Different Charts
   |    |-- tables           # Implements DataTables
   |    |-- tasks            # Celery, async processing
   |
   |-- templates/            # UI templates 
   |-- static/               # Tailwind/Flowbite 
   |    |-- src/             # 
   |         |-- input.css   # CSS Styling
   |
   |-- Dockerfile            # Docker
   |-- docker-compose.yml    # Docker 
   |
   |-- render.yml            # CI/CD for Render
   |-- build.sh              # CI/CD for Render 
   |
   |-- manage.py             # Django Entry-Point
   |-- requirements.txt      # dependencies
   |-- .env                  # ENV File
   |
   |-- *************************************************      
```   

<br />

## License

[Company License](https://github.com/app-generator/license-company)

<br />

---
[Rocket Django PRO](https://appseed.us/product/rocket-pro/django/) - Premium Seed Project styled with `Tailwind/Flowbite` actively supported by **[AppSeed](https://appseed.us)**.

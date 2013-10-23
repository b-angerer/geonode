The different ways to start your own geonode project
====================================================

Option 1
--------

You've installed GeoNode in dev mode and just want to test and modify GeoNode.

**Steps**

* Activate GeoNode’s Virtual Environment
	$ source /path/to/.venvs/geonode/bin/activate
* Create your GeoNode project from the template
	$ django-admin.py startproject my_geonode --template=https://github.com/GeoNode/geonode-project/archive/master.zip -epy,rst
	$ cd my_geonode
* Update your local_settings.py
* Synchronize your database
	$ python manage.py syncdb --all
* Run the test server and visit your site at http://localhost:8000
	$ pthon manage.py runserver
* theme your GeoNode

*additional*

* adding git repository
* staying in sync with mainline geonode using $ git fetch upstream master and $ git merge

Option 2
--------

You've installed GeoNode using apt-get and want to put it into production.

**Steps**

* Create your GeoNode project from the template	
	$ django-admin.py startproject my_geonode --template=https://github.com/GeoNode/geonode-project/archive/master.zip -epy,rst
	$ sudo pip install -e my_geonode
* make own github repository (additional)
* Edit the file /etc/apache2/sites-available/geonode and change WSGI Alias entry
* Restart apache
	$ sudo service apache2 reload
* Theme your geonode project; editing templates and css
* run collectstatic in your project folder
	$ python manage.py collectstatic
* staying in sync using
	$ apt-get update
	$ apt-get install geonode

Option 3
--------

You've installed GeoNode in dev mode and want to put it into production.
You've already configured GeoNode to use Apache, Tomcat, Postgresql etc.

**Steps**

* Activate GeoNode’s Virtual Environment
	$ source /path/to/.venvs/geonode/bin/activate
* Create your GeoNode project from the template
	$ django-admin.py startproject my_geonode --template=https://github.com/GeoNode/geonode-project/archive/master.zip -epy,rst
	$ cd my_geonode
* Update your local_settings.py
* Synchronize your database
	$ python manage.py syncdb --all
* Run the test server and visit your site at http://localhost:8000
	$ pthon manage.py runserver
* Edit the file /etc/apache2/sites-available/geonode and change WSGI Alias entry
* Restart apache
	$ sudo service apache2 reload
* theme your GeoNode
* run collectstatic in your project folder
	$ python manage.py collectstatic
* Restart apache
	$ sudo service apache2 reload
* some more changes in apache virtualhost ?

Questions
---------

* What if you've done the Complete Installation?
* Which additional changes in apache virtualhost have to be done?

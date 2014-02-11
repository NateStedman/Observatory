all:

run:
	./manage.py syncdb
	./manage.py runserver

migrate:
	./manage.py schemamigration dashboard --auto
	./manage.py schemamigration linked --auto
	./manage.py migrate dashboard
	./manage.py migrate linked
	./manage.py syncdb

clean:
	rm db.sqlite3
	rm -r dashboard/migrations
	rm -r linked/migrations
	./manage.py syncdb
	./manage.py schemamigration dashboard --initial
	./manage.py schemamigration linked -- initial
	./manage.py migrate dashboard --fake
	./manage.py migrate linked --fake
	./manage.py syncdb

start:
	sudo chmod +x ./manage.py
	./manage.py syncdb
	./manage.py schemamigration dashboard --initial
	./manage.py schemamigration linked -- initial
	./manage.py migrate dashboard 
	./manage.py migrate linked 
	./manage.py syncdb

fake:
	sudo chmod +x ./manage.py
	./manage.py syncdb
	./manage.py schemamigration dashboard --initial
	./manage.py schemamigration todo --initial
	./manage.py schemamigration emaillist --initial
	./manage.py migrate dashboard --fake
	./manage.py migrate todo --fake
	./manage.py migrate emaillist --fake
	./manage.py syncdb
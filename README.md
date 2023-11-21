# h5

PostgreSQL Install and One Table Database – SQL CRUD tutorial for Ubuntu

Three line install
$ sudo apt-get update
$ sudo apt-get -y install postgresql
$ sudo systemctl start postgresql # needed in 2023
$ sudo -u postgres createdb $(whoami)
$ sudo -u postgres createuser $(whoami)
The trick is to use your Linux system username for PostgreSQL database and PostgreSQL user. Then authentication is automatic.

$ psql

table

tero=> CREATE TABLE students (id SERIAL PRIMARY KEY, name VARCHAR(200));
CREATE TABLE

insert

tero=> INSERT INTO students(name) VALUES ('Tero');
INSERT 0 1

select

tero=> SELECT * FROM students;

update

tero=> UPDATE students SET name='Tero Karvinen' WHERE name='Tero';
UPDATE 1

delete

tero=> DELETE FROM students WHERE name='Liisa';
DELETE 1
tero=> SELECT * FROM students;

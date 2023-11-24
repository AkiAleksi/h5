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

SQL injection

SQL injection (SQLi) is a web security vulnerability that allows an attacker to interfere with the queries that an application makes to its database. This can allow an attacker to view data that they are not normally able to retrieve.

A successful SQL injection attack can result in unauthorized access to sensitive data, such as:

Passwords.
Credit card details.
Personal user information.

You can detect SQL injection manually using a systematic set of tests against every entry point in the application. 

a.)


![alku](https://github.com/AkiAleksi/h5/assets/112399816/194cd8be-a30c-43e2-a335-f66ab08e8ec7)





$ sudo -u postgres createdb kali


$ sudo -u postgres createuser kali





![alku3](https://github.com/AkiAleksi/h5/assets/112399816/59879e3a-48f4-4867-9e67-2102bd76bae2)



![1jee](https://github.com/AkiAleksi/h5/assets/112399816/d33a7880-6ad9-4c9e-b5be-d437df410e65)




![2jee](https://github.com/AkiAleksi/h5/assets/112399816/0d4d2d24-e0f2-4c7d-b2b1-3793d2d516b6)




![3jee](https://github.com/AkiAleksi/h5/assets/112399816/c6b810fb-84b6-487a-a866-d2884351726e)








![4jee](https://github.com/AkiAleksi/h5/assets/112399816/0d65a9ca-9814-4d9f-be7b-bd7765676269)


b.)

SELECT * FROM Users WHERE id = 10 OR 1=1;


The SQL above is valid and will return ALL rows from the "Users" table, since OR 1=1 is always TRUE.

id avain on valmiina ohjelmassa. Käyttäjän syöte on id:n arvo ja johon on jatkettu OR lause.


![xdddd](https://github.com/AkiAleksi/h5/assets/112399816/e7b429b9-d019-493d-a320-c45d753e8f7e)

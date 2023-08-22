# CREATING DATABASE

## CREATING TABLES

```SQL
CREATE TABLE album (
	album_id int NOT NULL AUTO_INCREMENT,
	album_name varchar(255),
	release_year int,
    	PRIMARY KEY (album_id)
);
```

```SQL
CREATE TABLE band (
	band_id int NOT NULL AUTO_INCREMENT,
    	band_name varchar(255) NOT NULL UNIQUE,
    	year_of_foundation year,
    	PRIMARY KEY (band_id)
);
```

``` SQL
CREATE TABLE genre (
	genre_id int NOT NULL AUTO_INCREMENT,
	genre_name varchar(255) UNIQUE,
    	PRIMARY KEY (genre_id)
);
```

``` SQL
CREATE TABLE instrument (
	instrument_id int NOT NULL AUTO_INCREMENT,
	instrument varchar(50) UNIQUE,
    	PRIMARY KEY (instrument_id)
);
```

```SQL
CREATE TABLE member (
	member_id int NOT NULL AUTO_INCREMENT,
	first_name varchar(50),
	nickname varchar(50),
	last_name varchar(50),
    	PRIMARY KEY (member_id)
);
```

``` SQL
CREATE TABLE song (
	song_id int NOT NULL AUTO_INCREMENT,
	track_number int,
	song_name varchar(255),
    	PRIMARY KEY (song_id)
);
```
## JUCTION TABLE

``` SQL
CREATE TABLE album_and_song (
	album_id int not null,
    	song_id int not null,
    	primary key (album_id, song_id),
    	constraint fk_album_id foreign key (album_id) references album(album_id),
    	constraint fk_song_id foreign key (song_id) references song(song_id)
);
```
### Juction table creation explained

![image](https://github.com/nina20126/My_cd_collection/assets/77397102/1452b6fc-48b3-4720-9c90-3e197ab5ee75)


Here we are creating a junction table called ```album_and_song```. This table makes it possible to create many to many relationships. In this case, an album can have many songs, and songs can belong to many albums. (For example, collection albums, special editions, EP's etc.) There are two fields in this table: ```album_id``` and ```song_id```. These two fields are also primary keys of the table.  

SQL constraints are used to specify rules for the data in a table. This table has two constraints, and they are named ```fk_album_id``` and ```fk_song_id```. Names could be basically anything, but it is common to include fk in the name and try to figure descriptive name.  

```album_id``` and ```song_id```that are values of the ```album_and_song``` table, are also foreign keys. The foreign key ```album_id``` references to the table called ```album``` (yellow) and that tables field called also ```album_id``` (yellow.) The second foreign key ```song_id``` references to the table called ```song``` (pink) and that tables field called also ```song_id``` (pink).

## INSERT DATA TO TABLES

``` SQL 
INSERT INTO song(track_number, song_name, duration)
values(1, "Divide",000404), 
(2, "Diaries",000332), 
(3, "Superstition",000351), 
(4, "Destroyer",000342), 
(5, "Surrender",000517), 
(6, "Oceania",000411), 
(7, "Rain",000346), 
(8, "Beyond",000351), 
(9, "The Other Side",000430), 
(10, "Trinity",000224);
```

``` SQL 
INSERT INTO album (album_name, release_year)
VALUES ("Superstition", 2014);
```

``` SQL 
INSERT INTO band_and_genre (band_id, genre_id)
VALUES (3,11),(3,12),(3,13);
```
When inserting data into a junction table, we use ID values. In this case, band_id and genre_id. ID's can be checked in reference tables using commands ```SELECT * FROM band``` (band_id) and ```SELECT * FROM genre``` (genre_id). 

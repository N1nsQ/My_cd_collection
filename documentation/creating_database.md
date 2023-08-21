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
	genre_name varchar(255),
    	PRIMARY KEY (genre_id)
);
```

``` SQL
CREATE TABLE instrument (
	instrument_id int NOT NULL AUTO_INCREMENT,
	instrument varchar(50),
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
CREATE TABLE band_and_album (
	band_id int not null,
    	album_id int not null,
    	primary key (band_id, album_id),
    	constraint band_fk foreign key (band_id) references band(band_id),
    	constraint album_fk foreign key (album_id) references album(album_id)
);
```

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

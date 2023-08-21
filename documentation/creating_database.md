# CREATING DATABASE

## CREATE TABLE

```SQL
CREATE TABLE album (
	album_id int NOT NULL AUTO_INCREMENT,
	album_name varchar(255),
	release_year int,
	band_id int,
	genre_id int,
	song_id int,
    	PRIMARY KEY (album_id)
);
```

```SQL
CREATE TABLE band (
	band_id int NOT NULL AUTO_INCREMENT,
    	band_name varchar(255) NOT NULL UNIQUE,
    	year_of_foundation year,
	genre_id int,
	album_id int,
	member_id int,
	song_id int,
    	PRIMARY KEY (band_id)
);
```

``` SQL
CREATE TABLE genre (
	genre_id int NOT NULL AUTO_INCREMENT,
	genre_name varchar(255),
	band_id int,
	album_id int,
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
	instrument_id int,
	band_id int,
    	PRIMARY KEY (member_id)
);
```

``` SQL
CREATE TABLE song (
	song_id int NOT NULL AUTO_INCREMENT,
	song_name varchar(255),
	band_id,
	album_id,
    	PRIMARY KEY (song_id)
);
```

## INSERT INTO

``` SQL 
INSERT INTO album (album_id, album_name, release_year, band_id, genre_id, song_id)
VALUES (null, 'Skid Row', 1989, null, null, null);
```

``` SQL 
INSERT INTO song (song_id, song_name, band_id, album_id, duration)
VALUES (null, 'Sweet little sister', null, null, '000310');
```

``` SQL 
INSERT INTO member (member_id, first_name, nickname, last_name, instrument_id, band_id)
VALUES (null, 'Dave', 'The Snake', 'Sabo', null, null);
```

``` SQL 
INSERT INTO instrument (instrument_id, instrument, member_id)
VALUES (null, 'lead vocals', null);
```



## ALTER TABLE

``` SQL
ALTER TABLE band
ADD CONSTRAINT FOREIGN KEY(genre_id) REFERENCES genre(genre_id);
```

## JUNCTION TABLES
``` SQL
CREATE TABLE member_and_instrument (
	member_id int not null,
    	instrument_id int not null, 
    	primary key(member_id, instrument_id),
    	constraint member_id_fk foreign key (member_id) references member(member_id),
    	constraint instrument_id_fk foreign key (instrument_id) references instrument(instrument_id)
);
```

``` SQL
CREATE TABLE band_and_album (
	band_id int not null,
    album_id int not null,
    primary key (band_id, album_id),
    constraint band_fk foreign key (band_id) references band(band_id),
    constraint album_fk foreign key (album_id) references album(album_id)
);
```

# CREATING DATABASE

## CREATE TABLE

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
INSERT INTO member (member_id, first_name, nickname, last_name, instrument, band_id)
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

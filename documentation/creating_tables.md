# CREATING TABLES

``` SQL
CREATE TABLE band (
	band_id int NOT NULL AUTO_INCREMENT,
    band_name varchar(250) NOT NULL,
    albums varchar(250),
    members varchar(250),
    genre varchar(150),
    songs varchar(250),
    year_of_foundation year,
    PRIMARY KEY (band_id),
    FOREIGN KEY (albums) REFERENCES band_and_album(album),
    FOREIGN KEY (members) REFERENCES band_and_member(member),
    FOREIGN KEY (genre) REFERENCES band_and_genre(genre),
    FOREIGN KEY (songs) REFERENCES band_and_song(song)
);

CREATE TABLE album (
	album_id int NOT NULL  AUTO_INCREMENT,
    album_name varchar(250) NOT NULL,
    band varchar(250),
    songs varchar(250),
    published year,
    PRIMARY KEY (album_id),
    FOREIGN KEY (band) REFERENCES band_and_album(band),
    FOREIGN KEY (songs) REFERENCES album_and_song(song)
);

CREATE TABLE member(
	member_id int NOT NULL  AUTO_INCREMENT,
    member_name varchar(250) NOT NULL,
    instrument varchar(150) DEFAULT 'unknown',
    band varchar(250),
    PRIMARY KEY (member_id),
    FOREIGN KEY (band) REFERENCES band_and_member(band)
);

CREATE TABLE song (
	song_id int NOT NULL  AUTO_INCREMENT,
    song_name varchar(250) NOT NULL,
    duration time,
    album varchar(250),
    band varchar(250),
    PRIMARY KEY (song_id),
    FOREIGN KEY (album) REFERENCES album_and_song(album),
    FOREIGN KEY (band) REFERENCES band_and_song(band)
);

CREATE TABLE genre (
	genre_id int NOT NULL AUTO_INCREMENT,
    genre varchar(150) NOT NULL,
    PRIMARY KEY (genre_id)
);

CREATE TABLE band_and_album (
	row_id int NOT NULL  AUTO_INCREMENT,
    band varchar(250),
    album varchar(250),
    PRIMARY KEY (row_id),
    FOREIGN KEY (band) REFERENCES band(band_name),
    FOREIGN KEY (album) REFERENCES album(album_name)
);

CREATE TABLE band_and_member (
	row_id int NOT NULL  AUTO_INCREMENT,
    band varchar(250),
    member varchar(250),
    PRIMARY KEY (row_id),
    FOREIGN KEY (band) REFERENCES band(band_name),
    FOREIGN KEY (member) REFERENCES member(member_name)
);

CREATE TABLE band_and_song (
	row_id int NOT NULL  AUTO_INCREMENT,
    band varchar(250),
    song varchar(250),
    PRIMARY KEY (row_id),
    FOREIGN KEY (band) REFERENCES band(band_name),
    FOREIGN KEY (song) REFERENCES song(song_name)
);

CREATE TABLE band_and_genre (
	row_id int NOT NULL  AUTO_INCREMENT,
    band varchar(250),
    genre varchar(150),
    PRIMARY KEY (row_id),
    FOREIGN KEY (band) REFERENCES band(band_name),
    FOREIGN KEY (genre) REFERENCES genre(genre)
);

CREATE TABLE album_and_song (
	row_id int NOT NULL  AUTO_INCREMENT,
    album varchar(250),
    song varchar(250),
    PRIMARY KEY (row_id),
    FOREIGN KEY (album) REFERENCES album(album_name),
    FOREIGN KEY (song) REFERENCES song(song_name)
);

CREATE TABLE album_and_genre (
	row_id int NOT NULL  AUTO_INCREMENT,
    album varchar(250),
    genre varchar(250),
    PRIMARY KEY (row_id),
    FOREIGN KEY (album) REFERENCES album(album_name),
    FOREIGN KEY (genre) REFERENCES genre(genre)
);
```

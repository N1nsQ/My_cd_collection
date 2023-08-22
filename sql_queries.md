# Examples of SQL queries

### Searching for a specific album and listing songs included

```SQL
select b.band_name, a.album_name, s.song_name, s.duration from band b
left join band_and_album baa on b.band_id = baa.band_id
left join album a on baa.album_id = a.album_id
left join album_and_song aas on a.album_id = aas.album_id
left join song s on s.song_id = aas.song_id
where a.album_name = Plastik';
```


<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/ad685ee1-740f-4e47-b431-0b05b545fc02" alt="result from the query above" width="400">

Joining tables band, album and song. Showing band name, album name, song name and song duration. Searching for album named "Plastik" and listing all songs that belongs to the album.

### Searching for all albums based on band_id

``` SQL
select b.band_name, a.album_name, a.release_year from album a
left join band_and_album baa on a.album_id = baa.album_id
left join band b on baa.band_id = b.band_id
where b.band_id = 1
order by a.release_year desc;
```
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/a0ed007a-d94c-48d9-acd9-63eb738e3021" alt="result from the query above" width="400">

Listing all albums that are related to band_id = 1. Albums are ordered based on release year. Showing columns band_name, album_name and release_year.

### Searching for some kind of metal music

```SQL
select a.album_name, a.release_year, g.genre_name from genre g
left join album_and_genre aag on g.genre_id = aag.genre_id
left join band_and_genre bag on g.genre_id = bag.genre_id
left join album a on a.album_id = aag.album_id
left join band b on b.band_id = bag.band_id
where genre_name like '%metal%';
```
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/803b768f-7622-4293-b2de-c67fefa01356" alt="result from the query above" width="400">

Searching from genres anything that includes "metal" in genre_name and then listing all albums with that match.

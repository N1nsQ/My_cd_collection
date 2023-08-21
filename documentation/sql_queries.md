# Examples of SQL queries

### Band member and instrument

``` SQL
select m.first_name, m.last_name, i.instrument from member m
left join member_and_instrument mai on m.member_id = mai.member_id 
left join instrument i on mai.instrument_id = i.instrument_id;
```
The command above shows all band members and their instuments. If a member plays multiple instruments, his/her name appears multiple times in the table.  
  
m is a reference to the member table  
i is a reference to the insrtument table  
mai is a reference to the member_and_istrument table  

### Band member and band
```SQL
select m.first_name, m.last_name, b.band_name from member m
left join band_and_member bam on m.member_id = bam.member_id
left join band b on bam.band_id = b.band_id;
```
The command below presents a table with all listed band members and bands they're playin.

```SQL
select b.band_name, m.first_name, m.last_name from band b
left join band_and_member bam on b.band_id = bam.band_id
left join member m on bam.member_id = m.member_id
where band_name = 'Skid Row';
```
The command below presents all band members who play in Skid Row.

### Band and album
```SQL
select b.band_name, a.album_name, a.release_year from album a
left join band_and_album baa on a.album_id = baa.album_id
left join band b on baa.band_id = b.band_id
where b.band_name = 'Skid Row';
```
Select all albums from Skid Row

### Band, album and song
```SQL
select b.band_name, s.song_name, a.album_name from band b
left join band_and_song bas on b.band_id = bas.band_id
left join song s on bas.song_id = s.song_id
left join band_and_album baa on b.band_id = baa.band_id
left join album a on baa.album_id = a.album_id
where b.band_name = 'Skid Row';
```
Table shows all Skid Row songs and which album they belog to.

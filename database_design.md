# Database Design

## Main tables

* Album 
* Band  
* Genre
* Instrument
* Member  
* Song  

## Relationships between tables

#### Band and Album 
* A band can have one or multiple albums. (Technically a band can exist without any albums, but it would't make sense to list it in cd collection if there is no album.)   
* An album must belong to a band. It can belong only to one band.  
* Relationship: **one to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/c8c1a737-d2c7-4e28-a552-1dfc567cf436" alt="relationship between band and album tables using crowsfoot notation" width="250">


#### Band and Member  
* A band can have many members, but it must have at least one member.
* A member can be a part of one or many bands, but at least one is required. (Otherwise he/she wouldn't be a band member)   
* Relationship: **many to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/c43112ae-32a1-4b79-ae81-9f13df938c13" alt="relationship between band and member tables using crowsfoot notation" width="250">


#### Band and Genre  
* A band can play in many genres, but at least one genre must be represented.
* One genre can be played by many artists, but it is also possible that nobody plays some of the genres.  
* Relationship: **many to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/c38bb2c8-1aa0-413f-84e9-084a2212d4f1" alt="relationship between band and genre tables using crowsfoot notation" width="250">


#### Band and Song  
* A band can have one or many songs. (Again, technically it is possible to have a band without any songs but it would't be logical to add that band in cd collection)
* One song can only belog to one band.  
* Relationship: **one to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/f41fc580-4e55-411a-aecb-a9f3620475ce" alt="relationship between band and song tables using crowsfoot notation" width="250">


#### Album and Song  
* An album can have one to many songs.
* A song can belong to many albums (A band might have collection albums, like "best of the bests" etc.)  
* Relationship: **many to many**
* Note! Several bands may have songs with same name (for example cover songs) so there might be songs with same name in the table.  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/a11d0eb2-a2c4-407e-9227-e89f29bb3285" alt="relationship between album and song tables using crowsfoot notation" width="250">


#### Album and Genre
* An album has only one main genre represented
* A genre can be represented in many albums or none of listed albums.
* Relationship: **one to many**
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/c03d0b62-9e59-465b-ae35-f925892426a0" alt="relationship between album and genre tables using crowsfoot notation" width="250">


#### Member and Insrtument
* It is very common that one band member handles more than just one instrument. A member could also play different instruments in different bands.
* An instrument can be played in several bands or none of listed bands.
* Relationship: **many tomany **
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/680e81dc-be10-46b4-ac7a-230f37925038" alt="relationship between member and instument tables using crowsfoot notation" width="250">


### Junction tables needed

* album_and_genre
* album_and_song
* band_and_album
* band_and_genre 
* band_and_member  
* band_and_song
* member_and_instrument


### Final EER Diagram from MySQL Workbench

![image](https://github.com/nina20126/My_cd_collection/assets/77397102/ed2b92bb-714c-4d3b-8178-0faca4a47e66)


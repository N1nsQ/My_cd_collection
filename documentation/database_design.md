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
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/fc02448e-5422-4bd6-9822-430fb2749630" alt="relationship between band and album tables using crowsfoot notation" width="250">  

#### Band and Member  
* A band can have many members, but it must have at least one member.
* A member can be a part of one or many bands, but at least one is required. (Otherwise he/she wouldn't be a band member)   
* Relationship: **many to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/b465363e-9489-46da-b0f0-558feec1ac83" alt="relationship between band and member tables using crowsfoot notation" width="250">  

#### Band and Genre  
* A band can play in many genres, but at least one genre must be represented.
* One genre can be played by many artists, but it is also possible that nobody plays some of the genres.  
* Relationship: **many to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/8b9a45e3-c7fc-46f1-a3d3-1237d36e69a2" alt="relationship between band and genre tables using crowsfoot notation" width="250">  

#### Band and Song  
* A band can have one or many songs. (Again, technically it is possible to have a band without any songs but it would't be logical to add that band in cd collection)
* One song can only belog to one band.  
* Relationship: **one to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/45d92ff1-97cb-42b2-b819-53e13e1597e4" alt="relationship between band and song tables using crowsfoot notation" width="250">  

#### Album and Song  
* An album can have one to many songs.
* A song can belong to many albums (A band might have collection albums, like "best of the bests" etc.)  
* Relationship: **many to many**
* Note! Several bands may have songs with same name (for example cover songs) so there might be songs with same name in the table.  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/c372ca32-0a04-4687-a155-a084b122573f" alt="relationship between album and song tables using crowsfoot notation" width="250">  

#### Album and Genre
* An album has only one main genre represented
* A genre can be represented in many albums or none of listed albums.
* Relationship: **one to many**
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/d50834c5-061f-40d0-8188-24464c418fb9" alt="relationship between album and genre tables using crowsfoot notation" width="250"> 

#### Member and Insrtument
* It is very common that one band member handles more than just one instrument. A member could also play different instruments in different bands.
* An instrument can be played in several bands or none of listed bands.
* Relationship: **many tomany **
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/7d790db4-23f0-4953-a3d1-a90bd87bc96b" alt="relationship between member and instument tables using crowsfoot notation" width="250">  


### Junction tables needed

* album_and_genre
* album_and_song
* band_and_album
* band_and_genre 
* band_and_member  
* band_and_song
* member_and_instrument


### Final EER Diagram from MySQL Workbench

![image](https://github.com/nina20126/My_cd_collection/assets/77397102/864a8979-73d0-4eea-9fbd-ac4c59b75cd8)

### Links
[Crow's Foot Notation](https://www.freecodecamp.org/news/crows-foot-notation-relationship-symbols-and-how-to-read-diagrams/)  


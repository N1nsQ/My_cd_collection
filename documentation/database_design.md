# Database Design

## Tables
Band  
Album  
Member  
Song  
Genre  

## Relationships between tables

#### Band and Album 
* A band can have one or multiple albums. (Technically a band can exist without any albums, but it would't make sense to list it in cd collection if there is no album.)   
* An album must belong to a band. It can belong only to one band.  
* Relationship: **one to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/fc02448e-5422-4bd6-9822-430fb2749630" alt="relationship between artists and albums table using crowsfoot notation" width="250">  

#### Band and Member  
* A band can have many members, but it must have at least one member.
* A member can be a part of one or many bands, but at least one is required. (Otherwise he/she wouldn't be a band member)   
* Relationship: **many to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/b465363e-9489-46da-b0f0-558feec1ac83" alt="relationship between artists and albums table using crowsfoot notation" width="250">  

#### Band and Genre  
* A band can play in many genres, but at least one genre must be represented.
* One genre can be played by many artists, but it is also possible that nobody plays some of the genres.  
* Relationship: **many to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/8b9a45e3-c7fc-46f1-a3d3-1237d36e69a2" alt="relationship between artists and albums table using crowsfoot notation" width="250">  

#### Band and Song  
* A band can have one or many songs. (Again, technically it is possible to have a band without any songs but it would't be logical to add that band in cd collection)
* One song can only belog to one band.  
* Relationship: **one to many**  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/45d92ff1-97cb-42b2-b819-53e13e1597e4" alt="relationship between artists and albums table using crowsfoot notation" width="250">  

#### Album and Song  
* An album can have one to many songs.
* A song can belong to many albums (A band might have collection albums, like "best of the bests" etc.)  
* Relationship: **many to many**
* Note! Several bands may have songs with same name (for example cover songs) so there might be songs with same name in the table.  
<img src="https://github.com/nina20126/My_cd_collection/assets/77397102/c372ca32-0a04-4687-a155-a084b122573f" alt="relationship between artists and albums table using crowsfoot notation" width="250">  


### Links
[Crow's Foot Notation](https://www.freecodecamp.org/news/crows-foot-notation-relationship-symbols-and-how-to-read-diagrams/)


# Database Design

## Tables
Artists  
Albums  
Members  
Songs  
Genre  

## Relationships between tables

**Artists** and **Albums**  
An artist can have multiple albums, but an album can only belong to one artist.  
Artist may exist without any album, but album always belogs to an artist.  
Relationship: **one to many**  
<br>
<img src="#" alt="relationship between artists and albums table using crowsfoot notation" width="200">


**Artists** and **Members**  
Artist (band) can have many members. A member can be a part of several bands.  
Band must have atleast one member and a member must play atleast in one band (otherwise he/she wouldn't be a band member)
Relationship: **many to many**
<br>
<img src="#" alt="relationship between artists and albums table using crowsfoot notation" width="200">


**Artists** and **Genre**  
An artist can play in many genres. One genre can be played by many artists.  
Relationship: **many to many**
<br>
<img src="#" alt="relationship between artists and albums table using crowsfoot notation" width="200">


**Artists** and **Songs**
An artist can have many songs. One song can only belog to one artist.  
Relationship: **one to many**
<br>
<img src="#" alt="relationship between artists and albums table using crowsfoot notation" width="200">


**Albums** and **Songs**
An album can have many songs. A song can belong to many albums (An artist might have collection albums, like "best of the bests" etc.)  
Relationship: **many to many**  
Note! Several artists may have songs with same name (for example cover songs) so there might be songs with same name in the table  
<br>
<img src="#" alt="relationship between artists and albums table using crowsfoot notation" width="200">


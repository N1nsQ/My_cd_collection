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

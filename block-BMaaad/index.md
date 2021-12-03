writeCode

Write command to

- List collections from a database.
-> show collections

- create a new collection in your country database which you created recently.
-> country.createCollection('newCollection');

Write code to:-

- crate a database named `weather`
-> use weather


- create a capped collection named `temperature` with maximum of 3 documents and try inserting more than 3 to see the result.
-> db.createCollection("temperature", {capped: true, size: 50000, max: 3})
   db.temperature.insert({'a' : 1})
   db.temperature.insert({'b' : 2})
   db.temperature.insert({'c' : 3})
   db.temperature.insert({'d' : 4})


- create a simple collection named `humidity`
-> db.createCollection('humidity')


- check whether `temperature` collection is capped or not ?
-> db.temperature.isCapped()


- Delete `humidity` collection and then the entire database(weather).
-> db.humidity.drop()

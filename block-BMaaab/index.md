writeCode

Run these shell commands in mongo shell:

- db.version()
- db.stats()
- db.help()

Write code to

- create a database of your country name.
-> use mycountryname
   db.user.insert({countryName: "INDIA"})

- check list of databases to see newly created database.
-> show dbs

- check which database you are currently connected to ?
-> db
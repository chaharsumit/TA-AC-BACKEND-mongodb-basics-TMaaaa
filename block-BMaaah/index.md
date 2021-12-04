writeCode

Write code to execute below expressions.

1. Create a database named `blog`.
-> use blog

2. Create a collection called 'articles'.
-> db.createCollection('articles')

3. Insert multiple documents(at least 3) into articles. It should have fields

- title as string
- createdAt as date
- details as String
- author as nested object
  - author should have
    - name
    - email
    - age
    - example author: {name: 'abc', email: 'abc@gmail', age: 25}
- tags : Array of strings like ['html', 'css']

var items = [
  {
    _id: 1,
    title: 'Responsive Web Design with HTML5 and CSS',
    details: 'a',
    author: {
      name: 'Ben Frain',
      email: 'abc@example.com',
      age: 50
    },
    tags: ['html', 'mongo', 'css']
  },
  {
    _id: 2,
    title: 'HTML & CSS: Design and Build Web Sites',
    details: 'ab',
    author: {
      name: 'John Duckett',
      email: 'abc@example.com',
      age: 40
    },
    tags: ['html', 'mongo', 'scss']
  },
  {
    _id: 3,
    title: 'JavaScript and JQuery: Interactive Front-End Web Development',
    details: 'abc',
    author: {
      name: 'John Ducett',
      email: 'abc@example.com',
      age: 45
    },
    tags: ['js', 'mongo', 'jquery']
  },
  {
    _id: 4,
    title: 'Eloquent JavaScript: A Modern Introduction to Programming',
    details: 'abcd',
    author: {
      name: 'Marjin Haverbeke',
      email: 'abc@example.com',
      age: 30
    },
    tags: ['js', 'mongo', 'html']
  },
]

```js
// An article should look like in the database
{
  _id: 'some_random_id',
  title: '',
  details: '',
  author: {
    name: '',
    email: '',
    age: ''
  },
  tags: ['js', 'mongo']
}
```
-> db.articles.insertMany(items)

4. Find all the articles using `db.COLLECTION_NAME.find()`
-> db.articles.find()

5. Find a document using \_id field.
-> db.articles.findOne({_id: 2})

6. 1. Find documents using title
-> db.articles.find({title: 'Responsive Web Design with HTML5 & CSS'})

7. 2. Find documents using author's name field.
-> db.articles.find({"author.name": 'John Duckett'})

8. Find document using a specific tag.
-> db.articles.find({tags: 'js'})

9. Update title of a document using its \_id field.
-> db.articles.update({_id: 2}, {$set: {title: 'title has changed'}})

10. Update a author's name using article's title.
-> db.articles.update({title: 'title has changed'}, {$set: {"author.name": 'NA'}})

11. rename details field to description from all articles in articles collection.
-> db.articles.updateMany({}, {$rename: "details", "description"})

12. Add additional tag in a specific document.
-> db.articles.update(tags: {$push: "javaScript"})

13. Update an article's title using $set and without $set.
-> db.artciles.update({title: 'title has changed'}, {$set: {title: 'title changed again'}})
-> db.articles.update({title: 'title changed again'}, {title: 'title change once more and all other data got truncated'})

- Write the differences here ?
-> The difference is that when we use $set then the other data fields still remain untouched and the edited fields only show the change but in case we dont use $set then the other fields get deleted from the document and the updated field is the only one that remains but the `Object__id` still remains the same as earlier 

13. find an article using title and increment it's auhtor's age by 5.
-> db.articles.update({title: 'Eloquent JavaScript: A Modern Introduction to Programming'}, {$inc: {"author.age": 5}})

14. Delete a document using \_id field with `db.COLLECTION_NAME.remove()`.
-> db.articles.remove({_id: 4})

// Sample data

```js
let users = [
  {
    age: 49,
    name: "Maurice Brock",
    email: "wuk@hibpiz.ch",
    gender: "Female",
    sports: ["cricket", "football"],
    scores: [24, 35, 18, 16],
    weight: 45,
  },
  {
    age: 37,
    birthday: "7/15/1986",
    name: "Virgie Cunningham",
    email: "ezogafa@de.gm",
    gender: "Male",
    sports: ["football"],
    scores: [17, 35, 43],
    weight: 52,
  },
  {
    age: 48,
    birthday: "5/14/1961",
    name: "Alexander Holt",
    email: "han@mu.pe",
    gender: "Male",
    sports: ["cricket", "football", "TT"],
    scores: [24, 30, 16],
    weight: 55,
  },
  {
    age: 53,
    birthday: "11/15/1963",
    name: "Derek Dawson",
    email: "polril@now.de",
    gender: "Male",
    sports: ["cricket", "hockey"],
    scores: [20, 15, 38, 23],
    weight: 49,
  },
  {
    age: 34,
    birthday: "7/24/1964",
    name: "Cynthia Cobb",
    email: "wujjarpob@jecimpar.gu",
    gender: "Female",
    sports: ["cricket"],
    scores: [41, 17, 28],
    weight: 51,
  },
  {
    age: 33,
    birthday: "10/26/1982",
    name: "Isabella Atkins",
    email: "ononuzas@givhoz.ca",
    gender: "Female",
    sports: ["cricket", "football", "hockey", "TT"],
    scores: [14, 38, 29, 45, 20],
    weight: 49,
  },
  {
    age: 47,
    birthday: "10/12/1978",
    name: "Katharine Bryan",
    email: "zo@pebi.sa",
    gender: "Male",
    sports: ["TT", "hockey", "khokho"],
    scores: [27, 20, 34],
    weight: 58,
  },
  {
    age: 41,
    birthday: "1/28/1991",
    name: "Beatrice Fleming",
    email: "ufufsa@pujizren.tk",
    gender: "Female",
    sports: ["football", "khokho"],
    scores: [30, 20, 15, 29, 43],
    weight: 47,
  },
  {
    age: 26,
    birthday: "3/23/1998",
    name: "Tom Fields",
    email: "wasodjow@ofaba.gf",
    gender: "Female",
    sports: ["khokho"],
    scores: [37, 29, 18, 43, 49],
    weight: 50,
  },
  {
    age: 33,
    birthday: "11/14/1960",
    name: "Steve Ortega",
    email: "dupus@ca.ls",
    gender: "Female",
    sports: ["cricket", "football", "hockey"],
    scores: [12, 15, 20],
    weight: 51,
  },
  {
    age: 24,
    birthday: "1/5/1994",
    name: "Suraj Kumar",
    weight: 50,
    gender: "Male",
    sports: ["football", "cricket", "TT"],
  },
]
```

Insert above data into database to perform below queries:-

- Find all males who play cricket.
-> db.users.find({tags: 'cricket'})

- Update user with extra golf field in sports array whose name is "Steve Ortega".
-> db.users.update({name: 'Steve Ortega'}, tags: {$push: 'golf'}})

- Find all users who play either 'football' or 'cricket'.
-> db.users.find($or: [{tags: 'cricket'},{tags: 'football'}])

- Find all users whose name includes 'ri' in their name.
-> db.users.find()
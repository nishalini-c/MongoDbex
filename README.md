# MongoDbex
**1. Create a database called Movies.**
```
      use movies
```
**2. Create a collection called movie details.**
```
     db.createCollection("moviedetils")
```

**3. Create the above five movie documents into a movie details collection.**
```
  movies> db.moviedetails.insertMany([{Title:"Jurassic Park",Type:"Adventure",Director:"Steven Spielberg",ReleaseYear:1993},{Title:"Forrest Gump",Type:"Drama",Director:"Robert Zemeckies",ReleaseYear:1994}, 
 {Title:"Titanic",Type:"Romance",Director:"James Cameron",ReleaseYear:1997},{Title:"The Dark Knight",Type:"Action",Director:"Steven Spielberg",ReleaseYear:1993},{Title:"Avatar",Type:"Science Fiction",Director:"James 
  Cameron,"ReleaseYear:2009}
```


**4. List all documents created.**
```
       db.moviedetails.countDocuments()
```


**5. List James Cameron’s movies.**
```
     movies> db.moviedetails.find({Director:"James Cameron"},{_id:0,Type:0,Director:0,ReleaseYear:0})
       [ { Title: 'Titanic' }, { Title: 'Avatar' } ]
```



**6. List James Cameron’s movies released in 2009.**
```
   movies> db.moviedetails.find({ReleaseYear:2009})
         [
      {
    _id: ObjectId("654c83418d42846c861a83b6"),
    Title: 'Avatar',
    Type: 'Science Fiction',
    Director: 'James Cameron',
    ReleaseYear: 2009
      }
     ]
```

**7. Delete the movie which you don’t like.**
```
     movies> db.moviedetails.remove({Title:"The Dark Knight,"Type:"Action,"Director:"Steven Spielberg,"ReleaseYear:1993})
      Deprecation Warning: Collection.remove() is deprecated. Use deleteOne, deleteMany, findOneAndDelete, or bulkWrite.
           { acknowledged: true, deletedCount: 1 }
     movies> db.moviedetails.countDocuments()
    4
```


**8. Add the movie which is your favourite.**
```
          movies> db.moviedetails.insertOne({Title:"pansathanthiram",Type:"Story",Director:"barathy",ReleaseYear:2000})
              {
           acknowledged: true,
      insertedId: ObjectId("654c8e108d42846c861a83b7")
             }
```

**9.List movie directed by Christopher Nolan in 1994.**
```
      movies> db.moviedetails.find({ Director: "Christopher Nolan"},{ ReleaseYear: 1994 })
```

**10. List out the director’s Name in your document**
```
                 movies> db.moviedetails.distinct("Director")
                 [ 'James Cameron', 'Robert Zemeckies', 'Steven Spielberg', 'barathy' ]
```

     



        
       

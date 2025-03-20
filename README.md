## API Endpoints
Base URL: [`http://localhost:8080/animals`](http://localhost:8080/animals)


### [`/all`](http://localhost:8080/animals/all) (GET)
Gets a list of all Animals in the database.

#### Response - A JSON array of Animal objects.

 ```
[
  {
     "name": "bluejay",
     "scientificName": "cyanocitta cristata",
     "species": "bird",
     "habitat": "forest",
     "description": "a kind of bird"
  },
  {
     "name": "robin",
     "scientificName": "turdus migratorius",
     "species": "bird",
     "habitat": "forest",
     "description": "another kind of bird"
  }
]
```

### [`/{animalId}`](http://localhost:8080/animals/1) (GET)
Gets an individual Animal in the system. Each Animal is identified by a numeric `animalId`

#### Parameters
- Path Variable: `animalId` &lt;integer&gt; - REQUIRED

#### Response - A single Animal

```
{
     "name": "bluejay",
     "scientificName": "cyanocitta cristata",
     "species": "bird",
     "habitat": "forest",
     "description": "a kind of bird"
  }
```

### [`/namecontains`](http://localhost:8080/animals/namecontains?name=blue) (GET)
Gets a list of animals with a name that contains the given string.

#### Parameters
- query parameter: `name` &lt;String&gt; - REQUIRED

#### Response - A JSON array of Animal objects.

```
[
  {
    "animalId": 1,
    "name": "bluejay",
    "scientificName": "cyanocitta cristata",
    "species": "bird",
    "habitat": "forest",
    "description": "a kind of bird"
  },
  {
    "animalId": 5,
    "name": "blue whale",
    "scientificName": "balaenoptera musculus",
    "species": "mammal",
    "habitat": "oceans",
    "description": "the largest known animal to have ever existed"
  }
]
```

### [`/species`](http://localhost:8080/animals/species?name=bird) (GET)
Gets a list of animals for a named species.

#### Parameters
- query variable: `name` &lt;String&gt; - REQUIRED

#### Response - A JSON array of Animal objects.

```
[
  {
    "animalId": 3,
    "name": "meerkat",
    "scientificName": "suricata suricatta",
    "species": "mammal",
    "habitat": "plains",
    "description": "a moderately sized rodent that lives in large families"
  },
  {
    "animalId": 5,
    "name": "blue whale",
    "scientificName": "balaenoptera musculus",
    "species": "mammal",
    "habitat": "oceans",
    "description": "the largest known animal to have ever existed"
  }
]
```

### [`/new`](http://localhost:8080/animals/new) (POST)
Create a new Animal entry
 
#### Request Body
An animal object. Note that the animalId is auto assigned in the database so is not needed in the request.
```
{
  "name": "blue whale",
  "scientificName": "balaenoptera musculus",
  "species": "mammal",
  "habitat": "oceans",
  "description": "the largest known animal to have ever existed"
}
```
#### Response - The updated list of Animals.

```
[
  {
    "animalId": 1,
    "name": "bluejay",
    "scientificName": "cyanocitta cristata",
    "species": "bird",
    "habitat": "forest",
    "description": "a kind of bird"
  },
  {
    "animalId": 2,
    "name": "robin",
    "scientificName": "turdus migratorius",
    "species": "bird",
    "habitat": "forest",
    "description": "another kind of bird"
  },
  {
    "animalId": 3,
    "name": "meerkat",
    "scientificName": "suricata suricatta",
    "species": "mammal",
    "habitat": "plains",
    "description": "a moderately sized rodent that lives in large families"
  },
  {
    "animalId": 5,
    "name": "blue whale",
    "scientificName": "balaenoptera musculus",
    "species": "mammal",
    "habitat": "oceans",
    "description": "the largest known animal to have ever existed"
  }
]
```

### [`/update/{animalId}`](http://localhost:8080/animals/update/1) (PUT)
Update an existing Student.

#### Parameters
- Path Variable: `animalId` &lt;integer&gt; - REQUIRED

#### Request Body
An animal object with the updates.
```
{
  "name": "robin 2",
  "scientificName": "turdus migratorius",
  "species": "bird",
  "habitat": "forest",
  "description": "another kind of bird"
}
```
#### Response - the updated Animal object.
```
{
  "animalId": 1,
  "name": "robin 2",
  "scientificName": "turdus migratorius",
  "species": "bird",
  "habitat": "forest",
  "description": "another kind of bird"
}
```

### [`/delete/{animalId}`](http://localhost:8080/animals/delete/1) (DELETE)
Delete an existing Animal.

#### Parameters
- Path Variable: `animalId` &lt;integer&gt; - REQUIRED

#### Response - the updated list of Students.
```
[
  {
    "animalId": 2,
    "name": "robin",
    "scientificName": "turdus migratorius",
    "species": "bird",
    "habitat": "forest",
    "description": "another kind of bird"
  },
  {
    "animalId": 3,
    "name": "meerkat",
    "scientificName": "suricata suricatta",
    "species": "mammal",
    "habitat": "plains",
    "description": "a moderately sized rodent that lives in large families"
  },
  {
    "animalId": 5,
    "name": "blue whale",
    "scientificName": "balaenoptera musculus",
    "species": "mammal",
    "habitat": "oceans",
    "description": "the largest known animal to have ever existed"
  }
]
```

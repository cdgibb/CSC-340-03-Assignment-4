## API Endpoints
Base URL: [`http://localhost:8080/students`](http://localhost:8080/students)


### [`/all`](http://localhost:8080/students/all) (GET)
Gets a list of all Students in the database.

#### Response - A JSON array of Student objects.

 ```
[
  {
    "studentId": 1,
    "name": "Alice Smith",
    "major": "CSC",
    "gpa": 3.88
  },
  {
    "studentId": 2,
    "name": "Bobby Stewart",
    "major": "MAT",
    "gpa": 2.97
  }
]
```

### [`/{studentId}`](http://localhost:8080/students/1) (GET)
Gets an individual Student in the system. Each Student is identified by a numeric `studentId`

#### Parameters
- Path Variable: `studentId` &lt;integer&gt; - REQUIRED

#### Response - A single Student

```
{
  "studentId": 1,
  "name": "Alice Smith",
  "major": "CSC",
  "gpa": 3.88
}
```

### [`/name`](http://localhost:8080/students/name?search=ob) (GET)
Gets a list of students with a name that contains the given string.

#### Parameters
- query parameter: `search` lt;String&gt; - REQUIRED

#### Response - A JSON array of Student objects.

```
[
  {
    "studentId": 2,
    "name": "Bobby Stewart",
    "major": "MAT",
    "gpa": 2.97
  },
  {
    "studentId": 5,
    "name": "Jobadiah Evans",
    "major": "REL",
    "gpa": 3.46
  }
]
```

### [`/major/{major}`](http://localhost:8080/students/major/csc) (GET)
Gets a list of students for a named major.

#### Parameters
- path variable: `major` &lt;String&gt; - REQUIRED

#### Response - A JSON array of Student objects.

```
[
  {
    "studentId": 1,
    "name": "Alice Smith",
    "major": "CSC",
    "gpa": 2.97
  },
  {
    "studentId": 7,
    "name": "John Doe",
    "major": "CSC",
    "gpa": 3.65
  }
]
```

### [`/honors`](http://localhost:8080/students/honors?gpa=3.5) (GET)
Gets a list of students with a GPA meeting the Threshold.

#### Parameters
- query parameter: `gpa` &lt;Double&gt; - REQUIRED

#### Response - A JSON array of Student objects.

```
[
  {
    "studentId": 1,
    "name": "Alice Smith",
    "major": "CSC",
    "gpa": 3.88
  },
  {
    "studentId": 7,
    "name": "John Doe",
    "major": "CSC",
    "gpa": 3.65
  }
]
```

### [`/new`](http://localhost:8080/students/new) (POST)
Create  a new Student entry
 
#### Request Body
A student object. Note that the studentId is auto assigned in the database so is not needed in the request.
```
{
  "name": "Mister New Student",
  "major": "CSC",
  "gpa": 3.28
}
```
#### Response - The updated list of Students.

```
[
  {
    "studentId": 1,
    "name": "Alice Smith",
    "major": "CSC",
    "gpa": 3.88
  },
  {
    "studentId": 2,
    "name": "Bobby Stewart",
    "major": "MAT",
    "gpa": 2.97
  },
  {
    "studentId": 3,
    "name": "Mister New Student",
    "major": "CSC",
    "gpa": 3.28
  }
]
```

### [`/update/{studentId}`](http://localhost:8080/students/update/1) (PUT)
Update an existing Student.

#### Parameters
- Path Variable: `studentId` &lt;integer&gt; - REQUIRED

#### Request Body
A student object with the updates.
```
{
  "name": "Mister Updated Student",
  "major": "CSC",
  "gpa": 3.45
}
```
#### Response - the updated Student object.
```
{
  "studentId": 1,
  "name": "Mister Updated Student",
  "major": "CSC",
  "gpa": 3.45
}
```

### [`/delete/{studentId}`](http://localhost:8080/students/delete/1) (DELETE)
Delete an existing Student.

#### Parameters
- Path Variable: `studentId` &lt;integer&gt; - REQUIRED

#### Response - the updated list of Students.
```
[
  {
    "studentId": 2,
    "name": "Bobby Stewart",
    "major": "MAT",
    "gpa": 2.97
  },
{
    "studentId": 3,
    "name": "Mister Updated Student",
    "major": "CSC",
    "gpa": 3.28
  }
]
```

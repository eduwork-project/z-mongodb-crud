# z-mongodb-crud
## Description
Ini adalah kunci jawaban untuk pertanyaan tugas Database:Tugas_2

## Steps

### Create db
```
use DatabaseSekolah
```

### Create collections
```
db.createCollection("DataMember", {
   validator: {$jsonSchema: {
      bsonType: "object",
      properties: {
         name: {
            bsonType: "string",
            description: "must be a string"
         },
         role: {
            bsonType: "string",
            description: "must be a string"
         }
      }
   }}
})
```

### Create new document data (3 teachers and 5 students)
```
db.DataMember.insertMany([
{
  name: "Budi",
  role: "teacher"
},
{
  name: "Ani",
  role: "teacher"
},
{
  name: "Lisa",
  role: "teacher"
},
{
  name: "Alex",
  role: "student"
},
{
  name: "Firman",
  role: "student"
},
{
  name: "Ali",
  role: "student"
},
{
  name: "Nisa",
  role: "student"
},
{
  name: "Celine",
  role: "student"
},
])
```

### Update 2 students role to be teacher
```
db.DataMember.update({"name": "Firman"}, {$set: {"role": "teacher"}})
db.DataMember.update({"name": "Celine"}, {$set: {"role": "teacher"}})
```

### Add 4 new documents for students
```
db.DataMember.insertMany([
{
  name: "Fira",
  role: "student"
},
{
  name: "Theo",
  role: "student"
},
{
  name: "Baba",
  role: "student"
},
{
  name: "Fatimah",
  role: "student"
},
])
```

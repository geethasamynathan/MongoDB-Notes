
# MongoDB Query Operators with Examples

## ✅ Collection: `employees`

### 📄 Sample Documents:
use yourDatabaseName; // Replace with your actual database name
```json
db.employees.insertMany([
  {
    "_id": 1,
    "name": "Alice",
    "age": 30,
    "department": "HR",
    "salary": 5000,
    "skills": ["communication", "management"],
    "active": true
  },
  {
    "_id": 2,
    "name": "Bob",
    "age": 25,
    "department": "IT",
    "salary": 7000,
    "skills": ["javascript", "nodejs", "mongodb"],
    "active": false
  },
  {
    "_id": 3,
    "name": "Charlie",
    "age": 35,
    "department": "Finance",
    "salary": 6500,
    "skills": ["excel", "accounting"],
    "active": true
  },
  {
    "_id": 4,
    "name": "Diana",
    "age": 28,
    "department": "IT",
    "salary": 7200,
    "skills": ["python", "mongodb"],
    "active": true
  }
]);
```

```json
{
  "_id": 1,
  "name": "Alice",
  "age": 30,
  "department": "HR",
  "salary": 5000,
  "skills": ["communication", "management"],
  "active": true
}
{
  "_id": 2,
  "name": "Bob",
  "age": 25,
  "department": "IT",
  "salary": 7000,
  "skills": ["javascript", "nodejs", "mongodb"],
  "active": false
}
{
  "_id": 3,
  "name": "Charlie",
  "age": 35,
  "department": "Finance",
  "salary": 6500,
  "skills": ["excel", "accounting"],
  "active": true
}
{
  "_id": 4,
  "name": "Diana",
  "age": 28,
  "department": "IT",
  "salary": 7200,
  "skills": ["python", "mongodb"],
  "active": true
}
```

---

## 🔍 MongoDB Query Operators with Examples

---

### 1. `$eq` (equal to)
```js
db.employees.find({ department: { $eq: "IT" } })
```
**Explanation**: Finds employees whose `department` is exactly "IT".

---

### 2. `$ne` (not equal to)
```js
db.employees.find({ department: { $ne: "HR" } })
```
**Explanation**: Finds all employees not in the "HR" department.

---

### 3. `$gt` (greater than)
```js
db.employees.find({ age: { $gt: 30 } })
```
**Explanation**: Finds employees older than 30.

---

### 4. `$gte` (greater than or equal to)
```js
db.employees.find({ salary: { $gte: 7000 } })
```
**Explanation**: Finds employees whose salary is 7000 or more.

---

### 5. `$lt` (less than)
```js
db.employees.find({ salary: { $lt: 6000 } })
```
**Explanation**: Finds employees with salary less than 6000.

---

### 6. `$lte` (less than or equal to)
```js
db.employees.find({ age: { $lte: 28 } })
```
**Explanation**: Finds employees aged 28 or less.

---

### 7. `$in` (match any value from an array)
```js
db.employees.find({ department: { $in: ["IT", "Finance"] } })
```
**Explanation**: Finds employees in either IT or Finance departments.

---

### 8. `$nin` (not in array)
```js
db.employees.find({ department: { $nin: ["HR"] } })
```
**Explanation**: Finds employees whose department is not HR.

---

### 9. `$and` (combine multiple conditions)
```js
db.employees.find({ $and: [ { age: { $gt: 25 } }, { department: "IT" } ] })
```
**Explanation**: Finds IT employees older than 25.

---

### 10. `$or` (either condition)
```js
db.employees.find({ $or: [ { age: { $lt: 28 } }, { salary: { $gt: 7000 } } ] })
```
**Explanation**: Finds employees younger than 28 OR with salary over 7000.

---

### 11. `$not` (negate condition)
```js
db.employees.find({ age: { $not: { $gt: 30 } } })
```
**Explanation**: Finds employees whose age is **not greater than** 30.

---

### 12. `$exists` (check field existence)
```js
db.employees.find({ skills: { $exists: true } })
```
**Explanation**: Finds documents where the `skills` field exists.

---

### 13. `$type` (check field type)
```js
db.employees.find({ age: { $type: "int" } })
```
**Explanation**: Finds documents where `age` is of integer type.

---

### 14. `$all` (match all elements in array)
```js
db.employees.find({ skills: { $all: ["mongodb", "javascript"] } })
```
**Explanation**: Finds employees who have **both** `mongodb` and `javascript` skills.

---

### 15. `$size` (exact array length)
```js
db.employees.find({ skills: { $size: 2 } })
```
**Explanation**: Finds employees who have exactly 2 skills.

---

### 16. `$regex` (pattern matching)
```js
db.employees.find({ name: { $regex: "^A", $options: "i" } })
```
**Explanation**: Finds employees whose name starts with "A" (case-insensitive).

---

### 17. `$elemMatch` (condition on array elements)
```js
db.employees.find({ skills: { $elemMatch: { $eq: "mongodb" } } })
```
**Explanation**: Finds employees whose skills include `mongodb`.

---

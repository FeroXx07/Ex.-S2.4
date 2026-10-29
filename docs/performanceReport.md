1. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({}, {_id: 0})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


2. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({}, {restaurant_id: 1, name: 1, _id: 0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


3. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({}, {restaurant_id: 1, name: 1, borough:1 , cuisine: 1, _id: 0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


4. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({}, {restaurant_id: 1, name: 1, borough:1 , "address.zipcode": 1, _id: 0})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 664
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_DEFAULT

## ✅ No significant issues detected


5. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough: "Bronx"}, {_id: 0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 54
- 🔍 **Documents examined**: 54
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


6. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough: "Bronx"}, {_id: 0}).limit(5)`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 5
- 🔍 **Documents examined**: 5
- 🛠️ **Execution stage**: LIMIT

## ✅ No significant issues detected


7. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough: "Bronx"}, {_id: 0}).skip(5).limit(5)`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 5
- 🔍 **Documents examined**: 5
- 🛠️ **Execution stage**: LIMIT

## ✅ No significant issues detected


8. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find( { "grades.score": { $gt: 90 } }, { _id: 0 } )`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 2
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 2 (ratio 332.0:1)

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ grades.score: 1 });
```


9. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({grades: {$elemMatch: {score: {$gt: 80, $lt:100}}}}, { _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)


10. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"location.coordinates.1" : {$lt: -95.754168}}, { _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 0
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


11. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({cuisine: {$ne: "American"}, "grades.score": {$gt: 70}, "location.coordinates.0": {$lt: -65.754168}}, { _id: 0 })`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'cuisine' - performance may suffer.
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ cuisine: 1 });
db.restaurants.createIndex({ grades.score: 1 });
```


12. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({cuisine: {$ne: "American"}, "grades.score": {$gt: 70}, "location.coordinates.0": {$lt: -65.754168}}, { _id: 0 })`
- ⏱️ **Execution time**: 2 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'cuisine' - performance may suffer.
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ cuisine: 1 });
db.restaurants.createIndex({ grades.score: 1 });
```


13. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({cuisine:{$ne:'American'}, "grades.grade": "A", borough:{$ne:'Brooklyn'}}, { _id: 0 }).sort({cuisine: -1})`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 318
- 🔍 **Documents examined**: 535
- 🛠️ **Execution stage**: SORT

## ✅ No significant issues detected


14. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({ name: { $regex: "\^Wil" } }, { restaurant_id: 1, name: 1, borough: 1, cuisine: 1, _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 2
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 2 (ratio 332.0:1)


15. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({ name: { $regex: ".*ces$" } }, { restaurant_id: 1, name: 1, borough: 1, cuisine: 1, _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 2
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 2 (ratio 332.0:1)


16. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({ name: { $regex: ".*Reg.*" } }, { restaurant_id: 1, name: 1, borough: 1, cuisine: 1, _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 4
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 4 (ratio 166.0:1)


17. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough: "Bronx", cuisine: { $in: ["American", "Chinese"] } }, {_id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 22
- 🔍 **Documents examined**: 54
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


18. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough: {$in:["Staten Island", "Queens", "Bronx", "Brooklyn"]}},{ restaurant_id: 1, name: 1, borough: 1, cuisine: 1, _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 359
- 🔍 **Documents examined**: 359
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


19. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({borough: {$nin:["Staten Island", "Queens", "Bronx", "Brooklyn"]}},{ restaurant_id: 1, name: 1, borough: 1, cuisine: 1, _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 305
- 🔍 **Documents examined**: 305
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected


20. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"grades.score": {$lte:10}}, { restaurant_id: 1, name: 1, borough: 1, cuisine: 1, _id: 0 })`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 612
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ℹ️ Recommendations
- ‼️ Filtering on unindexed field 'grades.score' - performance may suffer.

### 💡 Suggested Indexes
Consider creating these indexes:
```javascript
db.restaurants.createIndex({ grades.score: 1 });
```


21. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({ $or: [{ cuisine: "Seafood" }, { cuisine: { $nin: ["American", "Chinese"] } }, { name: { $regex: "^Will" } }] }, { _id: 0 } )`
- ⏱️ **Execution time**: 1 ms
- 📚 **Documents returned**: 389
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: SUBPLAN

## ✅ No significant issues detected


22. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({grades: {$elemMatch:{grade:"A",score:11, date:ISODate("2014-08-11T00:00:00Z")}}},{restaurant_id: 1, name: 1, grades: 1, _id: 0})`
- ⏱️ **Execution time**: 0 ms
- 📚 **Documents returned**: 1
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## 🚨 Performance Issues

### ⚠️ High Priority Issues
- ⚠️ Examined 664 docs to return 1 (ratio 664.0:1)


23. ## 📊 Query Performance Report

- 🧪 **Query**: `db.restaurants.find({"grades.1.grade":"A","grades.1.score":9, "grades.1.date":ISODate("2014-08-11T00:00:00Z")},{restaurant_id: 1, name: 1, grades: 1, _id: 0})`
- ⏱️ **Execution time**: 2 ms
- 📚 **Documents returned**: 0
- 🔍 **Documents examined**: 664
- 🛠️ **Execution stage**: PROJECTION_SIMPLE

## ✅ No significant issues detected



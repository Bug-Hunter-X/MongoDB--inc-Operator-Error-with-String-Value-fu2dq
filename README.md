# MongoDB $inc Operator Error with String Value
This example demonstrates an error caused by providing a non-numeric value to the `$inc` operator in a MongoDB update query.  The `$inc` operator is designed to increment a numeric field by a specified value, and providing a string will cause the update to fail.

## Bug
The following JavaScript code demonstrates the incorrect usage of `$inc`:
```javascript
// Incorrect usage of $inc operator in MongoDB update query
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 'abc' } });
```
## Solution
The solution involves ensuring that the value passed to the `$inc` operator is a number:
```javascript
// Correct usage of $inc operator
db.collection('myCollection').updateOne({ _id: 1 }, { $inc: { count: 1 } });
```
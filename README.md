# Root
> a JSON database module

Examples

```js
const root = require("full.db")
const db = new root({
    "dbName": "test", // Our DB file name.
    "dbFolder": "database", // Our DB folder name.
    "noBlankData": true,
    "readable": true,
    "language": "en" // You can write "tr" or "en".
})

db.set("x.y.z", "abc") // abc

db.get("x") // {y: {z: "abc"}}
db.all() // {x: {y: {z: "abc"}}}

db.push("a", "hello") //  ["hello"]
db.push("a", "world") //  ["hello", "world"]
db.unpush("a", "hello") // ["world"]

db.push("b", {test: "fulldb"}) // [{test: "fulldb"}]
db.push("b", {test2: "fulldb2"}) // [{test: "fulldb"}, {test2: "fulldb2"}]
db.delByPriority("b", 1) // [{test2: "fulldb"}]
db.setByPriority("b", {newtest:"hey this is edited"} 1) // [{newtest:"hey this is edited"}]

db.delete("x") // true
db.deleteAll() // true
```


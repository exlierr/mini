# Object
```
name: "Tom"
nickname: "Tommy"
age: 21
favoriteColor: Color.Blue
```

# Array
```
brands: "Youtube", "Tiktok", "Spotify", "Twitter"
```

# Nesting Objects
```
name: "Tom"
nickname: "Tommy"
age: 21

coworker: <
  name: "Sam"
  nickname: "Sammy"
  age: 23
>
boss: <
  name: "Dave"
  nickname: "Davey"
  age: 39
>
```

# Full Example
```
class: "define"

abstract: "abs", < before: class >

interface: "impl", "interface", < "@class", 10.001, true >
static: "module"
```

# Json Equivalence
```json
{
    "class": "define",
    "abstract": ["abs", { "before": "define" }],
    "interface": ["impl", "interface", {"@class", 10.001, true},
    "static": "module",
}
```

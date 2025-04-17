# Mini Serialization Format Examples

---

## 🎯 Basic Key-Value Pairs
```mini
name: "Richard"
nickname: "Dick"
age: 28
```

### JSON Equivalent

```json
{
  "name": "Richard",
  "nickname": "Dick",
  "age": 28
}
```

---

## 🧵 String Concatenation (Implicit)
```mini
greeting: "Hello"
target: "World"
message: greeting " " target    // → "Hello World"
```

### JSON Equivalent

```json
{
  "greeting": "Hello",
  "target": "World",
  "message": "Hello World"
}
```

---

## ➕ Arithmetic Expressions
```mini
a: 10
b: 5
sum: a + b                    // → 15
area: a * b                   // → 50
```

### JSON Equivalent

```json
{
  "a": 10,
  "b": 5,
  "sum": 15,
  "area": 50
}
```

---

## 📁 File Path Assembly
```mini
folder: "/home/user"
filename: "data.txt"
fullPath: folder "/" filename  // → "/home/user/data.txt"
```

### JSON Equivalent

```json
{
  "folder": "/home/user",
  "filename": "data.txt",
  "fullPath": "/home/user/data.txt"
}
```

---

## 🔗 Referencing Other Keys
```mini
firstName: "Richard"
lastName: "Smith"
fullName: firstName " " lastName
```

### JSON Equivalent

```json
{
  "firstName": "Richard",
  "lastName": "Smith",
  "fullName": "Richard Smith"
}
```

---

## 📚 Arrays
```mini
languages: "English", "Spanish", "Japanese"
topLang: languages[0]   // → "English"
```

### JSON Equivalent

```json
{
  "languages": ["English", "Spanish", "Japanese"],
  "topLang": "English"
}
```

---

## 🧍 Nested Objects and Scoped Access
```mini
user: <
  name: "Richard"
  contact: <
    email: "richard@example.com"
  >
>

emailAddress: user.contact.email
```

### JSON Equivalent

```json
{
  "user": {
    "name": "Richard",
    "contact": {
      "email": "richard@example.com"
    }
  },
  "emailAddress": "richard@example.com"
}
```

---

## 🧮 Grouped Expressions
```mini
width: 1920
height: 1080
area: (width * height)         // → 2073600
```

### JSON Equivalent

```json
{
  "width": 1920,
  "height": 1080,
  "area": 2073600
}
```

---

## ✅ Summary
- Space-separated values = string concat
- `+`, `-`, `*`, `/` = numeric operations only
- Strings and numbers are compatible in concat
- Booleans, `null`, or undefined keys are not
- All values are evaluated by default
- Expressions may optionally be wrapped in parentheses for clarity

Use this format for configs, lightweight data, and anywhere you want clean expressive structure!

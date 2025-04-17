# Mini Serialization Format Examples

---

## 🎯 Basic Key-Value Pairs
```mini
name: "Taylor"
nickname: "Tay"
age: 28
```

### JSON Equivalent

```json
{
  "name": "Taylor",
  "nickname": "Tay",
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
firstName: "Kai"
lastName: "Ragan"
fullName: firstName " " lastName
```

### JSON Equivalent

```json
{
  "firstName": "Kai",
  "lastName": "Ragan",
  "fullName": "Kai Ragan"
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
  name: "Luna"
  contact: <
    email: "luna@example.com"
  >
>

emailAddress: user.contact.email
```

### JSON Equivalent

```json
{
  "user": {
    "name": "Luna",
    "contact": {
      "email": "luna@example.com"
    }
  },
  "emailAddress": "luna@example.com"
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

## 💥 Invalid Examples (For Reference)
```mini
truthy: true false             // ❌ Invalid — booleans not allowed in string concat
mix: "10" + 5                  // ❌ Invalid — cannot mix string and number in arithmetic
undefinedKey: notDefined       // ❌ Invalid — undefined references not allowed
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

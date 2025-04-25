
# 📦 Web File APIs Cheat Sheet

Everything you need to know about `FileReader`, `Blob`, and `FormData`—nicely categorized with icons for quick scanning!

---

## 🧩 FileReader

| 🧩 Feature              | 🔧 Type  | ⚙️ Method / Property       | 🎯 Description                     | 🎯 Values / Params                         |
|------------------------|----------|-----------------------------|------------------------------------|-------------------------------------------|
| 🏗 Constructor          | Class    | `new FileReader()`          | Initializes reader                 | Used with `<input type="file">`           |
| 🧠 Read as Text         | Method   | `.readAsText(file)`         | Reads file and returns text        | `file: Blob`                               |
| 🎨 Read as Data URL     | Method   | `.readAsDataURL(file)`      | Base64 encoded output              | Image preview, etc.                        |
| 🧊 Read as ArrayBuffer  | Method   | `.readAsArrayBuffer(file)`  | Binary buffer output               | WebSockets, crypto                         |
| 🧵 Read as Binary       | Method   | `.readAsBinaryString(file)` | **Deprecated** binary string       | Avoid in modern apps                       |
| 📍 onload               | Event    | `reader.onload`             | Triggered when read is done        | Access `reader.result` in callback         |
| ❌ onerror              | Event    | `reader.onerror`            | Triggered on failure               | Use for error handling                     |
| 🛑 Abort                | Method   | `.abort()`                  | Cancels reading                    |                                             |
| 📊 Progress             | Event    | `reader.onprogress`         | Tracks read progress               | `e.loaded`, `e.total`                      |

---

## 🧩 Blob

| 🧩 Feature              | 🔧 Type  | ⚙️ Method / Property          | 🎯 Description                     | 🎯 Values / Params                          |
|------------------------|----------|--------------------------------|------------------------------------|--------------------------------------------|
| 🏗 Constructor          | Class    | `new Blob(parts, options)`     | Creates a Blob object              | `parts: Array<string|BufferSource>`        |
| 📏 Size                 | Property | `.size`                        | Size in bytes                      | Read-only                                   |
| 🧾 Type                 | Property | `.type`                        | MIME type of Blob                  | Read-only (e.g. `image/png`, `text/html`)  |
| 📤 Convert              | Method   | `.slice(start, end, type)`     | Creates a blob slice               | Optional: `start`, `end`, `type`           |
| 🔄 Convert to URL       | Method   | `URL.createObjectURL(blob)`    | Temporary URL for preview          | Used for image previews                    |
| 🧽 Revoke URL           | Method   | `URL.revokeObjectURL(url)`     | Frees blob memory                  | Pass the blob URL                          |

---

## 🧩 FormData

| 🧩 Feature              | 🔧 Type  | ⚙️ Method / Property        | 🎯 Description                       | 🎯 Values / Params                       |
|------------------------|----------|-----------------------------|--------------------------------------|------------------------------------------|
| 🏗 Constructor          | Class    | `new FormData()`            | Initializes an empty FormData object | Optionally pass a `<form>` element       |
| ➕ Add Data             | Method   | `.append(key, value)`       | Adds field to form                   | `key: string`, `value: string | Blob`    |
| 📝 Set Data             | Method   | `.set(key, value)`          | Replaces field                       | Same as `.append()`                       |
| ❌ Delete Field         | Method   | `.delete(key)`              | Removes a key and its value          | `key: string`                             |
| 🔍 Check Field          | Method   | `.has(key)`                 | Checks if key exists                 | `key: string → boolean`                  |
| 🔁 Iterate              | Method   | `.entries()`                | Iterates `[key, value]` pairs        | Compatible with `for...of`               |
| 🔁 Keys                 | Method   | `.keys()`                   | Iterator of keys                     |                                           |
| 🔁 Values               | Method   | `.values()`                 | Iterator of values                   |                                           |
| 🔄 Submit               | Usage    | `fetch(url, { body: formData })` | Sends form via POST               | Used in file uploads, API forms           |

---

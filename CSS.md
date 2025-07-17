Here is a complete `.md` file that explains **CSS Pseudo-Elements**, **Pseudo-Classes**, and **All Selectors** in **raw CSS** format with practical examples.

---

````md
# 🎨 CSS Selectors, Pseudo-Classes, and Pseudo-Elements Guide

This markdown file provides a comprehensive reference for **CSS Selectors**, **Pseudo-Classes**, and **Pseudo-Elements** using raw CSS syntax and real-world examples.

---

## 📌 Basic CSS Syntax

```css
selector {
  property: value;
}
````

---

## 🔹 1. CSS Selectors (Core)

| Selector             | Description              | Example                              |
| -------------------- | ------------------------ | ------------------------------------ |
| `*`                  | Universal selector       | `* { margin: 0; }`                   |
| `element`            | Type selector            | `p { color: blue; }`                 |
| `.class`             | Class selector           | `.btn { padding: 10px; }`            |
| `#id`                | ID selector              | `#header { height: 50px; }`          |
| `element1, element2` | Grouping selector        | `h1, h2 { font-weight: bold; }`      |
| `element element`    | Descendant selector      | `div p { font-size: 16px; }`         |
| `element > element`  | Direct child             | `ul > li { list-style: none; }`      |
| `element + element`  | Adjacent sibling         | `h1 + p { margin-top: 10px; }`       |
| `element ~ element`  | General sibling          | `h1 ~ p { color: grey; }`            |
| `[attr]`             | Attribute selector       | `input[disabled] { opacity: 0.5; }`  |
| `[attr=value]`       | Specific attribute value | `a[target="_blank"] { color: red; }` |

---

## 🔸 2. Pseudo-Classes

Pseudo-classes define the **state of an element**.

```css
/* Hover example */
a:hover {
  text-decoration: underline;
}
```

### 📋 Common Pseudo-Classes

| Pseudo-Class      | Description                            |
| ----------------- | -------------------------------------- |
| `:hover`          | When user hovers                       |
| `:focus`          | Element is focused (e.g. input)        |
| `:active`         | Active link/button                     |
| `:visited`        | Visited link                           |
| `:checked`        | Checked checkbox/radio                 |
| `:disabled`       | Disabled form element                  |
| `:enabled`        | Enabled input                          |
| `:first-child`    | First child of parent                  |
| `:last-child`     | Last child of parent                   |
| `:nth-child(n)`   | nth child of parent                    |
| `:nth-of-type(n)` | nth of type among siblings             |
| `:not(selector)`  | Excludes elements                      |
| `:empty`          | Selects elements with no content       |
| `:required`       | Required input fields                  |
| `:optional`       | Optional input fields                  |
| `:is()`           | Matches any selector inside            |
| `:has()`          | Matches parent having a specific child |
| `:where()`        | Similar to `:is()`, no specificity     |

---

## 🧩 3. Pseudo-Elements

Pseudo-elements **style parts** of elements.

```css
/* Capital letter styling */
p::first-letter {
  font-size: 200%;
  color: red;
}
```

### 📘 Common Pseudo-Elements

| Pseudo-Element           | Description                              |
| ------------------------ | ---------------------------------------- |
| `::before`               | Insert content before element            |
| `::after`                | Insert content after element             |
| `::first-letter`         | First letter of the text block           |
| `::first-line`           | First line of the text block             |
| `::selection`            | Styling user-selected text               |
| `::placeholder`          | Placeholder text in inputs               |
| `::marker`               | List bullets or numbers in lists         |
| `::backdrop`             | Fullscreen dialog backdrop               |
| `::file-selector-button` | Upload input button styling              |
| `::cue`                  | Media cue text styling (e.g., subtitles) |

---

## 🧪 4. Advanced Examples

```css
/* Button hover */
button:hover {
  background-color: #333;
  color: white;
}

/* Odd table rows */
tr:nth-child(odd) {
  background-color: #f9f9f9;
}

/* Only first paragraph inside article */
article p:first-of-type {
  font-weight: bold;
}

/* Add an icon before each list item */
li::before {
  content: "✔️ ";
  color: green;
}

/* Placeholder styling */
input::placeholder {
  color: grey;
  font-style: italic;
}
```

---

## 🧠 Tips

* Use `::before` and `::after` with `content`.
* Pseudo-classes are **dynamic states** (like `:hover`), pseudo-elements are **static**.
* Combine selectors: `button:disabled::after { content: " (disabled)"; }`

---

## 📚 References

* [MDN CSS Pseudo-classes](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-classes)
* [MDN CSS Pseudo-elements](https://developer.mozilla.org/en-US/docs/Web/CSS/Pseudo-elements)
* [CSS Selectors Cheat Sheet](https://frontend30.com/css-selectors-cheatsheet/)

---

Happy Styling! 🎨

```

---

Let me know if you want this saved as a downloadable `.md` file or turned into a PDF for printing or notes.
```

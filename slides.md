---
# You can also start simply with 'default'
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: /assets/intro.jpg
# some information about your slides (markdown enabled)
title: Software Development | Foundations
info: |
  ## Software Development | Foundations
# apply unocss classes to the current slide
class: text-left
drawings:
  persist: false
transition: slide-left
mdc: true
---

# Validation, Error Handling, Middleware
Back-End Development - part 10/12
- [ ] validate using `express-validator` package
- [ ] Error Handling our routes
- [ ] Middleware

<div class="abs-br m-6 text-xl">
  <a href="https://github.com/slidevjs/slidev" target="_blank" class="slidev-icon-btn">
    <carbon:logo-github />
  </a>
</div>

<!--
-->

---
transition: slide-left
---

# Recap of Mongoose Validation (pg.1)

1. Create a simple `User` model with validation rules:
    ```js
    import mongoose from "mongoose";

    const userSchema = new mongoose.Schema({
      username: {
        type: String,
        required: true,
        minlength: 3,
        maxlength: 15,
      },
      email: {
        type: String,
        required: true,
        match: /^[\\w-\\.]+@([\\w-]+\\.)+[\\w-]{2,4}$/,
      },
      age: {
        type: Number,
        min: 13,
        max: 120,
      },
    });

    export const User = mongoose.model("User", userSchema);
    ```

---
transition: slide-left
---

# Mongoose Validation (pg.2)

1. In your Express route, handle validation errors:
    ```js
    app.post("/users", async (req, res) => {
      try {
        const user = new User(req.body);
        await user.save();
        res.status(201).send(user);
      } catch (err) {
        if (err.name === "ValidationError") {
          return res.status(400).send({ error: err.message });
        }
        res.status(500).send({ error: "Something went wrong" });
      }
    });
    ```

---
transition: slide-left
---

# Express Validation (pg.1)

1. Install and import express-validator: `npm install express-validator`
    ```js
    import express from "express";
    import { body, validationResult } from "express-validator";
      ```

1. Example `/register` route:
    ```js
    router.post(
      "/register",
      [
        body("username").notEmpty().withMessage("Username is required"),
        body("email").isEmail().withMessage("Must be a valid email"),
        body("password").isLength({ min: 6 }).withMessage("Password must be at least 6 characters"),
      ],
      (req, res) => {
        const errors = validationResult(req);
        if (!errors.isEmpty()) {
          return res.status(400).json({ errors: errors.array() });
        }
        res.send("User registered successfully!");
      }
    );
    ```

---
transition: slide-left
---

# Exercise: `express-validator` (pg.2)
Experiment the various validator methods

1. Use this base route to experiment with different validators:
```js
router.post("/test-inputs",
  [
    // Add different body() validators below
  ],
  (req, res) => {
    const errors = validationResult(req);
    if (!errors.isEmpty()) {
      return res.status(400).json({ errors: errors.array() });
    }

    res.send("Validation passed!");
  }
);
```

Go to next slide to view validator methods

---
transition: slide-left
---

# Explore express-validator: Validator methods (pg.3)

- General Validators: 
   - `.notEmpty()`  field must not be empty
   - `.isLength({ min, max })`  Check string length
   - `.equals(value)`	Check if field matches a specific value
- String & Email Validators
   - `.isEmail()`	Validates email address
   - `.isAlpha()`	Letters only
   - `.isAlphanumeric()`	Letters and numbers
   - `.isLowercase() / .isUppercase()`	All lowercase or uppercase
- Number Validators
   - `.isNumeric()`	Only numbers
   - `.isInt({ min, max })`	Integer within a range
   - `.isFloat({ gt, lt })`	Float range (greater than, less than)

Goto next slide for more validators...

---
transition: slide-left
---

# Explore express-validator: Validator methods (pg.4)

- URL / Data Validators
   - `.isURL()`	Checks if it's a valid URL
   - `.isJSON()`	Must be a valid JSON string
   - `.isBoolean()`	Accepts "true"/"false"
- Advanced / Custom
   - `.custom(fn)`	Your own logic (throw error or return true)
   - `.optional()`	Skip validation if field not present

---
layout: image-right
transition: slide-left
image: /assets/bos.png
backgroundSize: 500px 300px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:
- 🎸 [Default h1 styles are changing](https://developer.mozilla.org/en-US/blog/h1-element-styles)
- ⚡ [JSX Over the Wire](https://overreacted.io/jsx-over-the-wire/)
- 🩳 [Pocketbase](https://pocketbase.io/)
- 🔎 [SQL Noir](https://www.sqlnoir.com/)
- 🌤️ [Sunsetting Create React App](https://react.dev/blog/2025/02/14/sunsetting-create-react-app)

<br>
<hr>
<br>

- 🧪 [Enter anonymous lab questions](https://docs.google.com/forms/d/e/1FAIpQLSevvGARdHQikso-uLqFCO481MABKE5HofuSrlzEPMNQ2ZLykw/viewform?usp=dialog)
- ℹ️ [Course feedback survey](https://circuitstream.typeform.com/to/ZoyYk7px#course_id=SoftwareAN&instructor=9514)

<!-- 
- take attendance
-->

---
transition: slide-left
---

# Exercise:

<!--
-->

---
transition: slide-left
---

# Homework

- Make a To-Do List App with MongoDB [see instructions in LMS](https://courses.circuitstream.com/d2l/le/lessons/9514/topics/49825)
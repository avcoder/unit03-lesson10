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

# Express Validation, Error Handling, Middleware
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

# Recap
(5 min)

- My Github repo for Foodtruck App backend code 

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

# Group Exercises: Make rest of CRUD functionality
(remainder of time)  Take 10 mins to develop just one of the CRUD functionalities.  I'll take it up each 10 min interval.

1. Implement the rest of the TODOs I listed in the comments (Cmd + Shift + F > search for 'todo').  (i.e. router, controller, handler ...) 
   - delete (Exercise #1 - 10 mins)
   - create / post (Exercise #2 - 10 mins)
   - update / put  (Exercise #3 - 10 mins)
   - Stretch goal : implement the search box to search by name or receipt id


<!--
-->

---
transition: slide-left
---

# Homework

- REMINDER: There is a lab tomorrow
- Make a To-Do List App with MongoDB [see instructions in LMS](https://courses.circuitstream.com/d2l/le/lessons/9514/topics/49825)
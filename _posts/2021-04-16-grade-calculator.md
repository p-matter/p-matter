---
layout: post
title: Grade Calculator
---

# Grade Calculator

Calculate your grade in any class without the legwork. Just replace the content below with your own.

Want to track another class? Click the `•••` button at the top right of the table, then click `Duplicate`.

Your **Raw Score** is the grade you got without a late penalty. **Final Grade** calculates your late penalty.
You can hide the late penalty column after you make sure the amount is correct 🔮
If your late assignment was excused, **check off the "Excused" property** and your late penalty will be ignored ✨
The sum of grades beneath the **Weighted Grade** column is your grade in the class. 

[English 001](https://www.notion.so/9582686a5e6f45e88d9ee4606dcd62a4)

# How it works 🔎

Our formulas are based on a library called [math.js](https://mathjs.org/), but are setup to work without coding skills.

## **Days Late**

This formula calculates the number of days between the due date and submission.
In case of excused tardiness, correct the submission date or delete the formula and turn this column into a simple number.

```jsx
dateBetween(prop("Due"), prop("Submitted"), "days") * -1
```

## **Final Grade**

This formula takes late policies into consideration. It also accounts for any tardiness that's been excused.

```jsx
`prop("Grade") - prop("Days Late") * prop("Late Penalty") * 100 * toNumber(not prop("Excused"))`
```

## **Class Grade**

This formula calculates points per assignment. The sum is your grade in the class.

```jsx
`prop("Final Grade") * prop("Weighting")`
```

⚠ **Note**: If you modify any of the table's properties, you'll need to adjust the above formulas accordingly.
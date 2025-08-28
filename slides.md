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

# React Native
Mobile Development: Unit 08 - Lesson 01

- [ ] Aspects to Consider when Designing for Mobile
- [ ] MacOS vs Android
- [ ] Install Expo Go App on your phone

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

# Aspects to Consider 

- Designing for smaller screens means limited input types
- Must use responsive design to avoid clutter
- Input Types include touch, gestures, voice (due to no keyboard/mouse)
- Accessibility: High contrast, readable fonts, screen reader support
- 2 Major Ways to build mobile apps:
   - Native: Platform specific (ex: Swift for Mac vs Kotlin/Java for Android)
   - Cross-Platform: One codebase for both (ex: React Native, Flutter)
- What kind of phone do you have to test with?

---
transition: slide-left
---

# Set up Default React Native project (pg.1)

- Install Expo Go > if it asks to find/connect to devices on your local network > Allow
- `npx create-expo-app --help` (OK to proceed? say yes)
- `npx create-expo-app helloworld`
- Once you see `✅ Your project is ready` then:
   - `cd helloworld`
   - go to package.json to find out how to start via `npm`
   - fyi: How can I start it without using `npm`? 

---
transition: slide-left
layout: two-cols
---

# Set up Default React Native project (pg.2)

- a QR code comes up, scan it with your phone that already has Expo Go installed; should eventually see -->

## Exercise
- Take a moment to explore and poke around the folders/files
- Try changing `Welcome!` to `Hello World`
- Take 5 minutes and satisfy your curiosity
   - keep poking around, change/break stuff
- Report one thing you've discovered with the rest of the class in Zoom chat

::right::

<img src="/assets/rn1.jpeg" style="height: 500px; margin: 0 auto">

---
transition: slide-left
---

# Set up BLANK React Native project

- `npx create-expo-app note-app -t`
   - choose Blank (TS) when prompted
- `cd note-app`
- `npm start`
- scan QR code > should see app via Expo Go 
   - if using iPhone: use camera app to scan QR code
   - if using Android: use Expo Go app to scan QR code
   - ensure phone is connected on same wi-fi as your computer



---
transition: slide-left
---

# Set up Blank React Native project

- Question: How can I inspect/debug on mobile?
   - Answer #1 try shaking your phone
   - Answer #2 try 3 touch hold - iOS only > reveals debug menu

## Exercise 

- You can also expose your app to anywhere in the world via `npm start --tunnel`
   - good if you wish to share your work with a co-worker, friend or client
   - Let's try it!

---
transition: slide-left
---

# Expo Go Framework Overview

- Expo is an Open Source React Native framework
   - similar to how Next.js is a React Framework; Nuxt.js is a Vue Framework
   - https://react.dev/learn/creating-a-react-app#expo
- Vanilla React Native gives us components to render text, views, scrollable lists, etc.
- Vanilla React Native doesn't give us out of the box nav, push notifs, using camera etc.
- Expo provides of tools and libraries that are not provided out of the box 
- Expo Go is a small part of Expo, so it's NOT the same as Expo
- Expo Go is a "sandbox" designed for learning, prototyping but isn't recommended when building production apps. You can't customize native code with it. It is designed to quickly get started building apps without spending time setting up your native dev env.
- What do you use to build production mobile React Native apps?   [Development Builds](https://docs.expo.dev/develop/development-builds/introduction/)
- First four classes we'll use Expo Go.  Last 4 classes we'll eventually use Development Build.

---
transition: slide-left
---

# Linting and Prettier

- `npx expo lint` > choosing Yes creates `.eslint.config.js`
- `npx expo install -- --save-dev prettier eslint-config-prettier eslint-plugin-prettier`
- see https://docs.expo.dev/guides/using-eslint/
   ```js
  const { defineConfig } = require('eslint/config');
  const expoConfig = require("eslint-config-expo/flat");
  const eslintPluginPrettierRecommended = require("eslint-plugin-prettier/recommended"); // add this

  module.exports = defineConfig([
    expoConfig,
    eslintPluginPrettierRecommended, // add this
    {
      ignores: ["dist/*"],
    }
  ]);
   ```

- goto App.tsx, notice how it uses single quotes?  Save file > should automatically change to double quotes 

---
transition: slide-left
---

# Components: `<View>` `<Text>`

- `<View>` is like `<div>`, can have many of them, serves as a container tag for positioning and styling
  - unlike the web, everything in react native must be wrapped by a component
  - do NOT think of `<View>` as only one instance in existence (ex: MVC) - it's NOT that
- `<Text>` is like `<p>`; in React Native all text must be wrapped in a `<Text>`
   - this is because React Native will compile this appropriately to the UI elements based on the various platforms (ex: iOS, Android, etc)
- See the errors if you:
   1. put plain text
   1. put a Text component outside View
   1. use falsy values 

---
transition: slide-left
---

# Inline Styles

- similar to css on the web except:
   - no units; everything is display points
   - defined as valid JS objects
   - no CSS animations


---
layout: image-right
transition: slide-left
image: /assets/rn.png
backgroundSize: 444px 380px
class: text-left
---

# 10 minute break

🍦 Cool Tips, Trends and Resources:
- 👩‍💻 [React Native on FCC](https://www.freecodecamp.org/news/build-a-meditation-app-with-react-native-expo-router/)
- 📄 [UI: React Native Paper](https://reactnativepaper.com/)
- ⚛️ [UI: React Native Elements](https://reactnativeelements.com/)
- 🧭 [React Navigation](https://reactnavigation.org/)


<br>
<hr>
<br>

- 🧪 [Enter anonymous lab questions](https://docs.google.com/forms/d/e/1FAIpQLSevvGARdHQikso-uLqFCO481MABKE5HofuSrlzEPMNQ2ZLykw/viewform?usp=dialog)
- ℹ️ [Course feedback survey](https://circuitstream.typeform.com/to/ZoyYk7px#course_id=SoftwareAN&instructor=9514)

---
transition: slide-left
---

# Explore Expo Examples

1. `npx create-expo-app --help`
2. Find the command that allows you to choose an Expo example via `--example` flag
3. Pick an example to install from [this list](https://github.com/expo/examples?tab=readme-ov-file) and have fun poking around
4. Goto Step 2 and repeat to see/modify other examples 

---
transition: slide-left
---

# Homework

- Work on your "Algorithm and Structural Foundations" assignment due July 20 midnight EST
   - can submit before due date if you wish
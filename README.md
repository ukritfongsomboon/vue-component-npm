<!-- 📌📍📎📢🔎🚩🛠❌❓❗🎉🏁🏅💯💢💡 -->

# @ukrit.fb/vue-plugin-npm-example

เป็นตัวอย่างการเขียน Package ของ Javascript โดยในตัวอย่างจะเป็นการเขียน Vuejs UI Component เพื่อใช้งานโดยจะสร้าง UI Component เป็น Vue Plugin หลังจากนั้นจะ Build Package และ Publish ขึ้น

## 👉 ขั้นตอน

- Create Vuejs Project
- Create UI Component in Project
- Config Plugin
- Config Build Package
- Build Package
- Push Package to NPM
- Update Package
- Used Package from NPM

## 📎 Reference

- [Create & Publish you first Vue.JS Plugin on NPM (The Right Way) ](https://5balloons.info/create-publish-you-first-vue-plugin-on-npm-the-right-way/)
- [How to Create and Publish an NPM Package – a Step-by-Step Guide](https://www.freecodecamp.org/news/how-to-create-and-publish-your-first-npm-package/)
- [Creating a package.json file](https://docs.npmjs.com/creating-a-package-json-file)
- [Creating and publishing scoped public packages](https://docs.npmjs.com/creating-and-publishing-scoped-public-packages)
- [Getting 404 when attempting to publish new package to NPM](https://stackoverflow.com/questions/39115101/getting-404-when-attempting-to-publish-new-package-to-npm)
- [Vuejs Plugins](https://v2.vuejs.org/v2/guide/plugins.html)

# 📌 Getting started

## 1. Create Vuejs Project

เป็นขั้นตอนในการ Create Vuejs Project ด้วย Vue Cli

```
vue create <project-name>
```

### Compiles and hot-reloads for development

```
npm run serve
```

### Compiles and minifies for production

```
npm run build
```

### Lints and fixes files

```
npm run lint
```

### Customize configuration

See [Configuration Reference](https://cli.vuejs.org/config/).

## 2. Create UI Component in Project

## 3. Config Plugin

สร้างไฟล์​ `install.js` เพื่อใช้ในการ Export UI Component เป็น Vue Plugin โดยให้ไฟล์อยู่ใน `src/install.js` โดยในไฟล์จะมีข้อมูลดังนี้

```javascript
import ComponentA from './components/ComponentA.vue'
const HelloWorldSimple = {
  install(Vue, options) {
    Vue.component('ComponentA', ComponentA)
  },
}
if (typeof window !== 'undefined' && window.Vue) {
  window.Vue.use(HelloWorldSimple)
}
export default HelloWorldSimple
```

## 4. Config Build Package

แก้ไข `package.json` โดยมีการเพิ่ม

```json
{...
  "private": false,
  "main": "./dist/@ukrit.fb/vue-plugin-npm-example.common.js",
  "files": ["dist"],
  "publishConfig": {
    "access": "public"
  },
...}
```

และเพิ่ม Script ในการ Build Package

```json
{...
  "scripts":{...
    "build-library": "vue-cli-service build --target lib --name @ukrit.fb/vue-plugin-npm-example ./src/install.js",
  ...}
...}
```

## 5. Build Package
Run คำสั่งที่ใช้ในการ Build Package

``` sh
npm run build-library
```

## 6. Push Package to NPM

## 7. Update Package

## 8. Used Package from NPM

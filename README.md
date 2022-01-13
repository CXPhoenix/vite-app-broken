# About This Project
這是壞掉的...我一直無法順利運作 tailwindcss 的功能...**【狀況解決】**

## 解決的方案：

真的很...哀...我的腦洞開太大的了..

錯誤發生在 `tailwind.config.js` 中，

只要這樣修改：
```diff
module.exports = {
-  content: ['./index.html', './src/**/*.{js, jsx}'],
+  content: ['./index.html', './src/**/*.{js,jsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

看出問題了嗎?

沒錯，就是多一個空格...

因為那個是字串..字串..字串......

多空格，他就找不到了...

Orz

---

## 以下是我建置專案的步驟：

1. use npm build the vite application
```shell
npm init vite vite-app --template react
```

2. change the directory to 'vite-app' folder
```shell
cd vite-app
```

3. install the library
```shell
npm install
npm install -D tailwindcss postcss autoprefixer
npx tailwindcss init -p
```

4. set tailwind config
```diff
module.exports = {
-  content: [],
+  content: ['./index.html', './src/**/*.{js, jsx}'],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

5. set css file
```css
/* ./src/index.css */
@tailwind base;
@tailwind components;
@tailwind utilities;
```

6. run dev server
```shell
npm run dev
```

## **然後就壞掉了...**

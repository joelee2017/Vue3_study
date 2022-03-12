# Vue3_study

### 第2章 vue 的 ssr原理

- #### 單元 1 - 什麼是 spa ? 什麼是 ssr?

  - spa - 的 dom 元素都是由 js Render而成的，等 html 生成後，在讀 js ，具有讀取速度上的優勢，爬蟲一開始不會讀取 js 中的 html ，所以在 seo 上略低，但 spa 好處在更新速度快，譬後台網站或活動網站。

  - ssr - Server side Render 好在丟出， 具有 seo 上有略高的優勢，適合平台網站及需 seo 網站 上。

- #### 單元 2 - 什麼是 Nuxt ?

  - 為了讓 vue 更容易開發才誕生的

- #### 單元 3 - Nuxt SSR 原理解析

  - Vue Cli 在 bundle 時只會產生一份， Nuxt 會 bundle 兩份檔案 ， Client (User 看的內容) 、 Server (專門餵給搜尋引擎爬蟲)
  - 過去的網站都是採用後端 Render 方式，跟 Nuxt 有明顯的差異。

### 第 3 章 開始使用 Nuxt 吧

- #### 單元 1 - Nuxt 安裝及設定

  ```powershell
  npx create-nuxt-app <project-name>
  
  npx（NPM 5.2.0起默認安裝npx）
  ```

  建立專案

  ```powershell
  create-nuxt-app v4.0.0
  ✨  Generating Nuxt.js project in nuxt-test-joe
  ? Project name: nuxt-test-joe
  ? Programming language: JavaScript
  ? Package manager: Npm
  ? UI framework: None
  ? Nuxt.js modules: Axios - Promise based HTTP client
  ? Linting tools: (Press <space> to select, <a> to toggle all, <i> to invert selection)
  ? Testing framework: None
  ? Rendering mode: Universal (SSR / SSG)
  ? Deployment target: Server (Node.js hosting)
  ? Development tools: jsconfig.json (Recommended for VS Code if you're not using typescript)
  ? What is your GitHub username? joe lee
  ? Version control system: Git
  
  
  🎉  Successfully created project nuxt-test-joe
  
    To get started:
  
          cd nuxt-test-joe
          npm run dev
  
    To build & start for production:
  
          cd nuxt-test-joe
          npm run build
          npm run start
  ```

- #### 單元 3 - Nuxt 架構解析 - layouts (新版的 Layout 資料夾在 .nuxt  下) & assets

  ```json
   "scripts": {
      "dev": "nuxt", // 開發環境起dev的指令
      "build": "nuxt build", // 打包整個專案
      "start": "nuxt start", // 直接將打包出來的程式用 Node.js 起一個 server 服務起來
      "generate": "nuxt generate"
    },
  ```

  ```powershell
     ╭───────────────────────────────────────╮
     │                                       │
     │   Nuxt @ v2.15.8                      │
     │                                       │
     │   ▸ Environment: development          │
     │   ▸ Rendering:   server-side          │
     │   ▸ Target:      server               │
     │                                       │
     │   Listening: http://localhost:3000/   │
     │                                       │
     ╰───────────────────────────────────────╯
  
  i Preparing project for development                                                   17:04:50
  i Initial build may take a while                                                      17:04:50
  i Discovered Components: .nuxt/components/readme.md                                   17:04:50
  √ Builder initialized                                                                 17:04:50
  √ Nuxt files generated                                                                17:04:50
  
  √ Client
    Compiled successfully in 14.88s
  
  √ Server
    Compiled successfully in 13.16s
  ```

  - 新版的 Layout 資料夾在 .nuxt  下

- #### 單元 4 - Nuxt 架構解析 - static & assets (新版的需自行建立)

  - 兩者皆放靜態檔案譬圖片
  - 所有經過 Nuxt 編繹打包過後的檔案都要放在 assels 譬套件
  - 不需要  Nuxt 編繹打包過後的檔案都要放在 static 譬圖片

- #### 單元 5 - Nuxt 架構解析 - stroe & plugins & middleware 

  - middleware 中間層
  - plugins  自行撰寫套件存放區
  - stroe  Vuex的部份
  - 各資料夾用途說明
    - assets：需要被打包的資源，例如你的 images 等等
    - components：頁面的最小單位組件
    - layouts：頁面共用的版型，例如 header、 footer
    - middleware：進入頁面前需要做的中間層
    - pages：頁面放的地方，一個 .vue 就是一個頁面
    - plugins：自定義的nuxt套件的資料夾
    - static：靜態資源，不需要被打包的資源
    - store： Vuex所放的資料夾

- #### 單元 6 - Nuxt 的生命週期表

  - Nuxt Lifecycle ： https://nuxtjs.org/docs/concepts/nuxt-lifecycle


# 📦 @kwange/vue-sql-editor

[![License](https://img.shields.io/npm/l/oclif.svg)](https://github.com/oclif/oclif/blob/main/package.json)
<br><br>
![avatar](https://github.com/skayi/vue-sql-editor/blob/main/vue-sql-editor.png)

<br />

# 🗒 Description

Vue SQL Editor.
<br />
Programing with `VueJS 2.6`.

<br />

# ✨ Features

1. SQL highlight
2. SQL format
3. SQL prompt

<br />

# 🔨 Installation

```
npm install @kwange/vue-sql-editor --save
or
yarn add @kwange/vue-sql-editor
```

<br />

# 🏗 Usage

```javascript
import Vue from 'vue'
import SQLEditor from '@kwange/vue-sql-editor'

Vue.use(SQLEditor)

<SQLEditor v-model="sqlstr" :readOnly="false" />
or
<sql-editor v-model="sqlstr" :readOnly="false" />
```

<br/>
<br/>

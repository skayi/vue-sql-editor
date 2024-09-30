# 📦 @kwange/vue-sql-editor

[![License](https://img.shields.io/npm/l/oclif.svg)](https://github.com/oclif/oclif/blob/main/package.json)
<br><br>
![avatar](https://github.com/skayi/vue-sql-editor/blob/main/vue-sql-editor.png?raw=true)

<br />

# 🗒 Description

Vue SQL Editor (based on `Codemirror`)

<br />

# ✨ Features

1. SQL highlight
2. SQL format
3. SQL prompt
4. Custom config

<br />

# 🔨 Installation

```
npm install @kwange/vue-sql-editor
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

Replace the format button with slot:

```javascript
<SQLEditor v-model="sqlstr" :lineNumbers="false">
  <template slot="format"><span style="color: blue;">Format SQL</span></template>
</SQLEditor>
```

Custom config:

```javascript
showFormat: true | false
formatText: 'Format'
showHint: true | false
readOnly: true | false

mode: 'text/x-mariadb',
indentWithTabs: true | false,
smartIndent: true | false,
lineNumbers: true | false,
matchBrackets: true | false,
cursorHeight: 1,
lineWrapping: true | false,
extraKeys: { Ctrl: 'autocomplete' },
hintOptions: { completeSingle: false },
```

To change editor content example:

```javascript
<template>
  <div id="app">
    <SQLEditor v-if="visible" v-model="sqlstr" />
    <ul>
      <li :key="i" v-for="(str, i) in sqlList" @click="onClick(str)">
        {{ str }}
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'App',
  data() {
    return {
      visible: true,
      sqlList: [
        'SELECT * FROM app_state_record\n        WHERE appName = ?\n        AND platform = ?\n        AND stateType = ?',
        'INSERT INTO sql_statement_info (`appId`, `sqlCode`, `sqlStatement`, `createTime`, `updateTime`, `lastActiveTime`) VALUES (?, ?, ?, ?, ?, ?)',
        `select a.seller_id, a.seller_name, b.user_name, c.state from a, b, c where a.seller_name = b.seller_name and b.user_id = c.user_id and c.user_id = 17 and a.gmt_create BETWEEN DATE_ADD(NOW(), INTERVAL – 600 MINUTE) AND DATE_ADD(NOW(), INTERVAL 600 MINUTE) order by a.gmt_create；`,
      ],
      sqlstr: '',
    }
  },
  methods: {
    onClick(str) {
      this.visible = false
      this.sqlstr = str
      this.$nextTick(() => {
        this.visible = true
      })
    },
  },
}
</script>
```

<br/>

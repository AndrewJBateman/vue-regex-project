# :zap: Vue Regex Project

* Vue app to highlight matching search text in a string using a regular expression.
![GitHub repo size](https://img.shields.io/github/repo-size/AndrewJBateman/vue-regex-project?style=plastic)
![GitHub pull requests](https://img.shields.io/github/issues-pr/AndrewJBateman/vue-regex-project?style=plastic)
![GitHub Repo stars](https://img.shields.io/github/stars/AndrewJBateman/vue-regex-project?style=plastic)
![GitHub last commit](https://img.shields.io/github/last-commit/AndrewJBateman/vue-regex-project?style=plastic)

## :page_facing_up: Table of contents

* [:zap: Vue Regex Project](#zap-vue-regex-project)
  * [:page_facing_up: Table of contents](#page_facing_up-table-of-contents)
  * [:books: General info](#books-general-info)
  * [:camera: Screenshots](#camera-screenshots)
  * [:signal_strength: Technologies](#signal_strength-technologies)
  * [:floppy_disk: Setup](#floppy_disk-setup)
  * [:computer: Code Examples](#computer-code-examples)
  * [:cool: Features](#cool-features)
  * [:clipboard: Status & To-Do List](#clipboard-status--to-do-list)
  * [:clap: Inspiration](#clap-inspiration)
  * [:envelope: Contact](#envelope-contact)

## :books: General info

* The matching text is replaced with a HTML-wrapped equivalent that has a class that changes the background color.
* A regular expression is used to find and replace the matching search text.

## :camera: Screenshots

![Example screenshot](./img/highlighted-search-text.png).

## :signal_strength: Technologies

* [Vue framework v2](https://vuejs.org/)
* [Vuex v3](https://github.com/vuejs/vuex) a central location from which state data is stored, modified and accessed.
* [Vue CLI v3](https://github.com/vuejs/vue-cli)
* [Vue DevTools extension for Chrome](https://chrome.google.com/webstore/detail/vuejs-devtools/nhdogjmejiglipccpnnnanhbledajbpd) was useful for debugging and seeing what was happening with the state when Vuex was used.

## :floppy_disk: Setup

* Run `npm run dev` for a dev server. Navigate to `http://localhost:8080/`. The app will automatically reload if you change any of the source files.

## :computer: Code Examples

* extract of `<script>` from App.vue

```javascript
export default {
  name: 'app',

  // inialise 2 variables, query = user input, content = text to be searched.
  data () {
    return {
      query: '',
      content: 'Lorem ipsum dolor sit amet, consectetur adipiscing elit. Suspendisse dignissim leo massa, sed aliquet leo posuere ut. Curabitur malesuada accumsan erat, id varius eros tincidunt quis. Vivamus lobortis, odio at fermentum efficitur, risus est tincidunt nisl, eget condimentum tellus dui vitae nibh. Donec id lorem condimentum, porttitor augue in, fermentum leo. Morbi condimentum, nunc ut malesuada placerat, sem nulla condimentum purus, iaculis tristique metus diam lobortis enim. Suspendisse potenti. Quisque urna magna, porta eget erat ac, pharetra vehicula erat. Suspendisse sed nisi ex.'
    }
  },

  // If query empty just return.
  // function highlight() is called if query is not empty.
  // It highlights query text by changing the class around the matching text.
  methods: {
    highlight () {
      if (!this.query) {
        return this.content
      }
      return this.content.replace(new RegExp(this.query, 'gi'), match => {
        return '<span class="highlightText">' + match + '</span>'
      })
    }
  }
}

```

## :cool: Features

* search for any text string within the lorem ipsum text supplied and it will be highlighted in bright green.

## :clipboard: Status & To-Do List

* Status: Tested and 100% working.
* To-Do: nothing

## :clap: Inspiration

* [Nic Raboy of X-Team.com: "Highlighting Text Within a String Using Vue.js and Regular Expressions"](https://x-team.com/blog/highlight-text-vue-regex/)

## :file_folder: License

* This project is licensed under the terms of the MIT license.

## :envelope: Contact

* Repo created by [ABateman](https://github.com/AndrewJBateman), email: gomezbateman@yahoo.com

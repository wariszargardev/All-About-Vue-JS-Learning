# Priority A Rules: Essential

# 1- Multi-word component name expect root components

## Bad Practice
```sh
<!-- in pre-compiled templates -->
<Item />

<!-- in in-DOM templates -->
<item></item>
```
## Good Practice

```sh
<!-- in pre-compiled templates -->
<TodoItem />

<!-- in in-DOM templates -->
<todo-item></todo-item>
```

# 2- Props defination should always be as details possibles
## Bad Practice
```sh
// This is only OK when prototyping
const props = defineProps(['status'])
```
## Good practice
```sh
const props = defineProps({ status: String }) 
```
## Even better!

```sh
const props = defineProps({
  status: {
    type: String,
    required: true,

    validator: (value) => {
      return ['syncing', 'synced', 'version-conflict', 'error'].includes(
        value
      )
    }
  }
})
```

# 3- Use keyed v-for
## Bad Practice
```sh
<ul>
  <li v-for="todo in todos">
    {{ todo.text }}
  </li>
</ul>
```

## Good Practice
```sh
<ul>
  <li
    v-for="todo in todos"
    :key="todo.id"
  >
    {{ todo.text }}
  </li>
</ul>
```

# 4- Avoid v-if with v-for 
## Bad Practice
```sh
<ul>
  <li
    v-for="user in users"
    v-if="user.isActive"
    :key="user.id"
  >
    {{ user.name }}
  </li>
</ul>
```
## Good Practice
```sh
<ul>
  <template v-for="user in users" :key="user.id">
    <li v-if="user.isActive">
      {{ user.name }}
    </li>
  </template>
</ul>

```

# 5- Use component-scoped styling
## Bad Practice
```sh
<template>
  <button class="btn btn-close">×</button>
</template>

<style>
.btn-close {
  background-color: red;
}
</style>
```
## Good Practice
```sh
<template>
  <button class="button button-close">×</button>
</template>

<!-- Using the `scoped` attribute -->
<style scoped>
.button {
  border: none;
  border-radius: 2px;
}

.button-close {
  background-color: red;
}
</style>
```




# Priority B Rules: Strongly Recommended
# 1-Component files

## Whenever a build system is available to concatenate files, each component should be in its own file.

## Bad Practice
``` sh
app.component('TodoList', {
  // ...
})

app.component('TodoItem', {
  // ...
})
```

## Good Practice
```sh
components/
|- TodoList.js
|- TodoItem.js

components/
|- TodoList.vue
|- TodoItem.vue
```


# 2- Single-file component filename casing
## Filenames of Single-File Components should either be always PascalCase or always kebab-case.

## Bad Practice
```sh
components/
|- mycomponent.vue
```

## Good Practice

```sh
components/
|- my-component.vue
```


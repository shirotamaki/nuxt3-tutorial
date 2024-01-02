<template>
  <div>
    <ul>
      <li v-for="user in users" :key="user.id">
        {{ user.id }}, {{ user.name }}

      </li>
    </ul>
      <h1>hoge</h1>
      <p>{{ users[0].id }}, {{ users[0].address }}</p>
  </div>
</template>

<script setup>
const { data: users, error } = await useFetch('https://jsonplaceholder.typicode.com/users')
console.log(error.value)
if (error.value) {
  throw createError({ statusCode: 404, statusMessage: 'Page not found !!!!!!!!!!'})
}
</script>

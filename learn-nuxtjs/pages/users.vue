<template>
  <div>
    <ul>
      <li>
        <nuxt-link to="/users">User Page</nuxt-link> |
        <nuxt-link to="/users/1">Details User</nuxt-link> |
        <nuxt-link to="/users/settings">Users Settings</nuxt-link>
      </li>
    </ul>
      <h1>Users Page (users.vue)</h1>
      <nuxt-child></nuxt-child>
  </div>
</template>

<script>
export default {
  middleware: ['check-visit'],
  layout(context){
    console.log("User layout: " + Object.keys(context))
    const isMobile = context.isMobile;
    if(isMobile){
      return 'mobile'
    }
    return 'admin';
  }
}
</script>

<style>
a.nuxt-link-exact-active {
  color: red !important
}
ul li{
  list-style-type: none;
}
</style>
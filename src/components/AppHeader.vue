<template>
  <div>
      <nav>
          <ul>
              <li><router-link :to="{name: 'Homepage'}">Home</router-link></li>
              <li><router-link :to="{name: 'Notes'}">Notes</router-link></li>
              <li><router-link :to="{name: 'Users'}">Users</router-link></li>
              <li><router-link :to="{name: 'Login'}">Login</router-link></li>
          </ul>
        </nav>
  </div>
</template>

<script>
export default {
  name:'app-header'
}
</script>

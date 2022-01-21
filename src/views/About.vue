<template>
  <div class="ul ul_profile">
    <Loader v-if="loader"/>
    <Accounts v-else v-bind:account="account"/>
  </div> 
</template>

<script>
import Accounts from '../components/Accounts.vue'
import Loader from '../components/Loader.vue'

export default {
  components: {
    Accounts,
    Loader
  },
  data() {
    return {
      account: {},
      loader: false
    }
  },
  mounted() {
    fetch('https://random-data-api.com/api/users/random_user')
          .then(data => data.json())
          .then(data => {
            this.loader = true
            setTimeout(() => {
              this.account = data
              this.loader = false
            }, 1000)
          })
  }
}
</script>



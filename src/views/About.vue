<template>
  <ul class="ul">
    {{account}}
    <Accounts v-bind:account="account"/>
  </ul> 
</template>

<script>
import Accounts from '../components/Accounts.vue'
export default {
  components: {
    Accounts
  },
  data() {
    return {
      account: {}
    }
  },
  mounted() {
    fetch('https://random-data-api.com/api/users/random_user')
          .then(data => data.json())
          .then(data => this.account = data)
  }
}
</script>
<!--
<script>
import Account from '../components/Account.vue'
import Loader from '../components/Loader.vue'

export default {
  name: 'Account',
  components: {
    Account,
    Loader
  },
  data() {
    return {
      account: {},
      loader: false
    }
  },
  methods: {
    getProfile() {
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
    },
  mounted() {
    fetch('https://random-data-api.com/api/users/random_user')
      .then(data => data.json())
      .then(data => this.account = data) 
  }
}


</script>

-->




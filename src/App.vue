<template>
  <div>
    <Contacts :contacts="contacts"/>
  </div>
</template>

<script>
import Contacts from './components/Contacts.vue'

export default {
  name: 'App',
  components: {
    Contacts,
  },
  data() {
    return {
      contacts: [],
    }
  },
  computed: {
    sorteArray() {
      let sortedContacts = this.contacts;

      sortedContacts = sortedContacts.sort((a,b) => {
        let fa = a.name.toLowerCase(), fb = b.name.toLowerCase();
        if (fa < fb) {
          return -1
        }
        if (fa > fb) {
          return 1
        }
        return 0
      })
	  }
  },
  methods: {
    async getContacts() {
      const res = await fetch('https://jsonplaceholder.typicode.com/users')
      .then(response => response.json())

      this.contacts = res;
      this.sorteArray;
    },
  },
  
  beforeMount(){
    this.getContacts()
    },
}
</script>

<style>
*{
  background: #000;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
    <div :key="contact.id" v-for="contact in contacts" v-bind:id="contact.id">
        <Contact :contact="contact" />
    </div>
</template>

<script>
import Contact from './Contact.vue'

export default {
    name: 'Contacts',
    props: {
        contacts: Array
    },
    components: {
        Contact
    }
}
</script>
<template>
  <v-conteiner>
    <v-layout align-content-space-around justify-start column>
      <message-form :messageAttr="message" />
      <message-row v-for="message in sortedMessages"
                   :key="message.id"
                   :message="message"
                   :editMessage="editMessage" />
    </v-layout>
  </v-conteiner>
</template>
<script>
  import { mapGetters } from 'vuex'
  import MessageRow from '../components/messages/MessageRow.vue'
  import MessageForm from '../components/messages/MessageForm.vue'

  export default {
    components: {
      MessageRow,
      MessageForm
    },
    data() {
      return {
        message: null
      }
    },
    computed: mapGetters(['sortedMessages']),
      methods: {
        editMessage(message) {
          this.message = message
        }
      }
  }

</script>
<style>


</style>
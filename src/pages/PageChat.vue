<template>
  <q-page class="flex column">
    <div class="q-pa-md column col justify-end">
      <q-chat-message
        v-for="message in messages"
        :key="message.text"
        :name="message.from"
        :text="[message.text]"
        sent
      />
    </div>
    <q-footer elevated>
      <q-toolbar>
        <q-input
          v-model="newMessage"
          bg-color="white"
          class="full-width"
          outlined
          rounded
          label="Message"
          dense
        >
          <template v-slot:after>
            <q-btn round dense flat color="white" icon="send" />
          </template>
        </q-input>
      </q-toolbar>
    </q-footer>
  </q-page>
</template>

<script>
export default {
  data() {
    return {
      newMessage: '',
      messages: [
        {
          text: 'hi Amr',
          from: 'me',
        },
        {
          text: 'good',
          from: 'them',
        },
        {
          text: 'you are sexy',
          from: 'me',
        },
      ],
    };
  },
};
</script>

<style></style>

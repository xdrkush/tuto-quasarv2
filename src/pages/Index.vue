<template>
  <q-page class="flex flex-center">

    <div v-for="(user, users) in array" :key='users'>
      <!-- btn -->
      <q-btn :label="user.lastName" color="primary" @click="showModal(user)" />
    </div>

    <!-- Modal -->
    <ModalTest v-if='modalTest' :modalTest="modalTest" :data='user' @closeModalTest='closeModal()' />

  </q-page>
</template>

<script>
import { defineComponent, ref } from 'vue'
import ModalTest from 'components/modal.vue'

export default defineComponent({
  name: 'PageIndex',

  components: {
    ModalTest
  },

  methods: {
    showModal (user) {
      console.log('Modal open 1', this.modalTest, user)
      this.user = user
      this.modalTest = true
    },
    closeModal () {
      console.log('Modal close 1', this.modalTest)
      this.modalTest = false
      this.user = null
    }
  },

  setup () {
    const array = [{ name: 'Dr', lastName: 'Kush' }, { name: 'Dr', lastName: 'Hsuk' }]
    const user = ref({})
    const modalTest = ref(false)
    return { modalTest, array, user }
  }
})
</script>

<template>
  <div class="q-pa-md q-gutter-sm">
    <q-dialog v-model='modal'>
      <q-card>
        <q-card-section>
          <div class="text-h6">hello {{ data.name }} {{ data.lastName }}</div>
        </q-card-section>

        <q-separator />

        <q-card-actions align="right">
          <q-btn flat label="Decline" color="primary" @click="$emit('closeModalTest')" />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
  props: ['modalTest', 'data'],
  setup (props) {
    console.log('log', props)
    const modal = ref(props.modalTest)
    return {
      modal
    }
  }
}
</script>

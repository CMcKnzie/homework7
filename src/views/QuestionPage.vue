<script setup>

import { ref, onMounted } from 'vue'
import useAPI from '@/composables/useAPI';
import { useRoute } from 'vue-router';

const api = useAPI()
const question = ref(null)
const route = useRoute()

onMounted(async () => {
  question.value = await api.getQuestion(route.params.id)

} )

</script>

<template>
  <div class="text-black">
{{ question }}
  </div>
</template>

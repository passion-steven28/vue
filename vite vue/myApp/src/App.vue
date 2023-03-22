<template>
    <modal
      :header="'welcome to vue passion'"
      :text="'lorem'"
      />
</template>

<script>
import modal from './components/modal.vue'


export default {
  name: 'app',
  components: {modal},
  
  methods: {
    handleClick(){
      console.log(this.$refs.name.value)
    }
  }
}
</script>
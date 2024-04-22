<template>
  <div>
    <h2>반응형 메시지</h2>
    <p>{{ reactiveMessage }}</p>
    <button v-on:click="addReactiveMessage">Add Message</button>
    <h2>일반 메시지</h2>
    <p>{{ normalMessage }}</p>
    <button v-on:click="addNormalMessage">Add Message</button>
  </div>
</template>


<script>
import { ref } from 'vue';

export default{
  setup(){
    const reactiveMessage = ref('Hello Reactive Message');
    const addReactiveMessage = () => {
      reactiveMessage.value = reactiveMessage.value + '!';
    };

    let normalMessage = 'Hello Normal Message';
    const addNormalMessage = () => {
      normalMessage = normalMessage + '!';
    };

    return {
      reactiveMessage,
      normalMessage,
      addReactiveMessage,
      addNormalMessage,
    }
  }
};
</script>


<style>

</style>

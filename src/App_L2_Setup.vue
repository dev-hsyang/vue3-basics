<template>
    <div>
        <p>
            {{  counter }}
        </p>
        <p>
            {{  message }}
        </p>
        <button @click="increment">
            increment counter!
        </button>
    </div>
</template>

<script>
import { ref } from 'vue';

    export default {
        setup(){
            const counter = ref(0);
            const increment = () => {
                counter.value += 1;
            };

            const message = ref('hello vue3');
            
            return{
                counter,
                message,
                increment,
            };
        },
    };
</script>

<style lang="scss" scoped>

</style>
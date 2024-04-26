<template>
    <div>
        <button v-on:click="increment">Count: {{ state.count }}</button>
        <br>
        <button v-on:click="deepIncrement">Deep Count: {{ state.deep.count }}</button>
    </div>
</template>

<script>
import { reactive } from 'vue';
export default {
    setup () {
        // 반응형 객체 생성하기 
        const state = reactive({
            count : 0,
            deep : {
                count : 0,
            },
        });

        const increment = () => {
            state.count++;
        };

        const deepIncrement = () => {
            state.deep.count++;
        };
        
        return {
            state,
            increment,
            deepIncrement
        };
    },
};
</script>

<style lang="scss" scoped>

</style>
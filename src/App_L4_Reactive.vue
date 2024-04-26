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
        // ref() 와 달리 reactive() 는 객체를 생성한다. 객체변수명 자체는 string 값이기 때문에
        // 아래의 경우 state 값 자체를 바꾸어도 동적으로 DOM 에 업데이트 되지 않는다.
        // 그러므로 아래와 같이 객체 내부의 변수를 바꾸어야 한다.
        const state = reactive({
            count : 0,
            deep : {
                count : 0
            }
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
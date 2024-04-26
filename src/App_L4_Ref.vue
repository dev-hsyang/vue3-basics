<template>
    <div>
        <p>
            {{ message }}
        </p>
        <button v-on:click="addMessage">add message</button>
    </div>
</template>

<script>
import { ref }  from 'vue';
export default {
    setup () {
        // ref()는 primitive 타입 변수를 반응형으로 만들 때 사용한다.
        let message = ref('Hello World!');

        const addMessage = () => {
            // script 에서 ref타입 반응형 변수의 값에 접근할 때는 .value 를 통해 접근해야 한다.
            // template 에서는 자동으로 unwrapping 되어 변수명으로 값 접근이 가능하다.
            message.value = message.value + '!';
        };

        console.log(message);
        console.log('message: ' , message.value);
        console.log('message type: ' , typeof message.value);

        return {
            message,
            addMessage,
        };
    },
};
</script>

<style lang="scss" scoped>

</style>
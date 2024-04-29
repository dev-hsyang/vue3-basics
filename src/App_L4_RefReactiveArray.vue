<template>
    <div>

    </div>
</template>

<script>
import { reactive, ref } from 'vue';

export default {
    setup () {
        // ref() 를 reactive 객체 내에서 사용하기
        const count = ref(0);
        const state = reactive({
            count,
        });

        count.value++;
        count.value++;
        console.log('count.value: ' , count.value);
        console.log('state.count: ' , state.count); // reactive 객체 내에서 ref 는 unwrap 이 된다.

        // ref() 를 array 내에서 사용하기
        const message = ref('Hello, world!');
        const arr = reactive([message]);
        console.log('arr[0]: ', arr[0].value); // 배열 내에서는 ref 가 unwrap 되지 않는다.
        
        return {}
    }
}
</script>

<style lang="scss" scoped>

</style>
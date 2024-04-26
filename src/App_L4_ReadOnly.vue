<template>
    <div>

    </div>
</template>

<script>
import { reactive, readonly } from 'vue';
export default {
    setup () {
        const original = reactive({
            count: 0,
        });

        const copy = readonly(original);
        original.count++;

        console.log('original: ' , original.count);
        console.log('copy: ' , copy.count); // original.count 와 함께 증감이 된다.

        copy.count++; // readonly 속성이기 때문에 값 변경은 불가하다

        return {
            original,
            copy,
        }
    }
}
</script>

<style lang="scss" scoped>

</style>
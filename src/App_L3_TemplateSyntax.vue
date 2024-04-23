<template>
    <div>
        <h2>보간법</h2>
        <p>
            {{ message }}
        </p>
        <p v-once>
            {{ message }}
        </p>
        <button v-on:click="message = message + '!'">
            Click Me!
        </button>
        <hr>
        <h2>v-html</h2>
        <p v-html="rawHtml">
        </p>
        <hr>
        <h2>속성 바인딩</h2>
        <div v-bind:title="dynamicTitle">
            마우스를 올려보세요!
        </div>
        <!-- v-bind 는 자주/많이 사용되기 때문에, v-bind:에서 v-bind를 생략하고 : 으로 단축해서 사용할 수 있다. -->
        <input type="text" value="vi-binding" :disabled="isInputDisabled"/>
        <!-- 다중 속성 바인딩 -->
        <input :="attrs" />
        <hr>
        <h2>JavaScript 표현식 사용도 가능합니다.</h2>
        {{ message.split('').reverse().join('') }}
        <br>
        {{ isInputDisabled ? '예' : '아니오'}}
    </div>
</template>

<script>
import { ref } from 'vue';

export default {
    setup () {
        const message = ref('안녕하세요!');
        const rawHtml = ref('<strong>안녕하세요</strong>');
        const dynamicTitle = ref('안녕하세요~!~!');
        const isInputDisabled = ref(true);
        // 다중 속성 바인딩
        const attrs = ref({
            type : "password",
            value : "1234567",
            disabled : false,
        });

        return {
            message,
            rawHtml,
            dynamicTitle,
            isInputDisabled,
            attrs,
        };
    },
}
</script>

<style lang="scss" scoped>

</style>
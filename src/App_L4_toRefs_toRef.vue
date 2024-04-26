<template>
    <div>
        <p>author: {{ author }}</p>
        <p>title: {{  title  }}</p>
    </div>
</template>

<script>
import { reactive, toRefs, toRef } from 'vue';

    export default {
        setup(){
            const book = reactive({
                author: 'Vue Team',
                year: '2020',
                title: 'Vue 3.0',  
                description: 'Vue 3.0 guide',
                price: 'free',
            });

            // 반응형 객체의 구조를 분해해서 변수에 할당할 시 반응성을 잃게 된다.
            // 따라서 toRefs(), toRef() 를 활용해 반응성을 유지시키며 받아와야한다.
            const { author, title } = toRefs(book); // 다수 속성 가져오기
            const author2 = toRef(book, 'author'); // 하나의 속성 가져오기
            const title2 = toRef(book, 'title');
            
            return{
                author,
                title,
                author2,
                title2,
                book,
            };
        }

    };
</script>

<style lang="scss" scoped>

</style>
<template>
    <div>
        <HelloWord :friend="giang.firstName"/>
        <div>
            {{ count }}
        </div>
        <div>
            <button @click="hello">hello</button>
        </div>

    </div>
</template>

<script lang="ts">
import { defineComponent } from 'vue';
import HelloWord from './components/HelloWord.vue';

export default defineComponent({
    data() {
        return {
            name: 'Tran Bao Giang',
            giang: {
                firstName: 'Tran',
                lastName: 'Giang',
            },
            count: 0
        }
    },
    methods: {
        hello() {
            this.count++;
        }
    },
    computeds: {
        fullName() {
            return this.giang.firstName + this.giang.lastName;
        }
    },
    watch: {
        count(value){
            console.log(value)

        }
    },
    beforeCreate(){

    },
    components: {
        HelloWord
    }
})
</script>
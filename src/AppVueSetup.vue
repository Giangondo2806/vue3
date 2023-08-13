<template>
  <div>
    <HelloWord :friend="fullName" @update="update"/>
    <div>
      {{ test }}
    </div>
    <div>
      <button @click="hello">hello</button>
    </div>

  </div>
</template>

<script setup lang="ts">
import { reactive, ref, computed, watch, onMounted, onUpdated, onBeforeMount } from 'vue';
import HelloWord from './components/HelloWord.vue';
// ref // string. boolean. number. object
// goi thong qua value, name.value, count.value
const name = ref('Tran Bao Giang');
const count = ref(0);

// reactive object
const giang = reactive({
  firstName: 'Tran',
  lastName: 'Giang'
})

//method
const hello = () => {
   count.value++;
}

const update  = (ev: string)=>{
  console.log(ev);
}

// computed
const fullName = computed(() => {
  return giang.firstName + giang.lastName;
})

const test = computed(()=>{
  return count.value *2;
})
// watch
watch(giang, (value)=>{
  console.log('value', giang);
})

onMounted(() => {
  console.log('mouted');
})


onUpdated(()=>{
  console.log('updated')
})

onBeforeMount(()=>{
  console.log('before-mount')
}) 




</script>




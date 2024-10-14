<template>
    <div style="background-color:#aaaa">
        <div>
            <title>HTML Code:</title>
            <input placeholder="Input HTML Code" v-model="htmlCode" type="text" style="width:300px;height:300px">
        </div>
       <div>
            <title>LESS Code:</title>
            <input placeholder="Input LESS Code" v-model="lessCode" type="text" style="width:300px;height:300px">
       </div>
        
        <div v-html="htmlCode" :style="compileLess"></div>
        <div v-if="errorMessage" style="color: red;">{{ errorMessage }}</div>
        
    </div>
</template>
<script setup>
import {ref} from 'vue';
import less from 'less';

const htmlCode=defineModel('htmlCode');
const lessCode=defineModel('lessCode');
const dynamicStyles = ref({});
const errorMessage = ref(''); 
const compileLess = async () => {
  try {
    const output = await less.render(lessCode);
    
    dynamicStyles.value = output.css;
    errorMessage.value = '';
  } catch (error) {
    errorMessage.value = error.message;
    dynamicStyles.value = {};
  }
};
</script>
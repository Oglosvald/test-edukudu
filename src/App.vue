<script setup>
import Child from './components/Child.vue';
import InputToHtml from './components/InputToHtml.vue';
import {ref} from 'vue';

const title = ref('Test');
const bool = ref(false);
const htmlCode = ref('');
const lessCode = ref('');
</script>

<template>

    
  
  <div class="wrapper">

    <main style="background-color:rgba(0, 0, 0, 0.2)">
      <p>Parent title: {{ title }}</p>
      <p>Parent bool: {{ bool }}</p>
      <div style="background-color:rgba(0, 0, 0, 0.7);margin-top?20px">
        <Child v-model:title="title" v-model:bool="bool"/>


      </div>
      <div>

        <InputToHtml v-model:htmlCode="htmlCode" v-model:lessCode="lessCode"/>
      </div>
    </main>
    
  </div>
 
  

</template>

<style scoped>
header {
  line-height: 1.5;
}

.logo {
  display: block;
  margin: 0 auto 2rem;
}

@media (min-width: 1024px) {
  header {
    display: flex;
    place-items: center;
    padding-right: calc(var(--section-gap) / 2);
  }

  .logo {
    margin: 0 2rem 0 0;
  }

  header .wrapper {
    display: flex;
    place-items: flex-start;
    flex-wrap: wrap;
  }
}
</style>

<script setup>
  import { provide, computed, ref, onMounted, watch } from 'vue';
  import Header from './components/Header.vue'
  import MyComponent from './components/MyComponent.vue';
  import CompInheritClass from './components/CompInheritClass.vue';
  import CompProvideInject from './components/CompProvideInject.vue';

  provide('fullname', 'Gregory Doud provided as fullname');
  const fn = ref("Greg");
  const ln = ref("Doud");
  const showName = ref(true);
  const items = ref(["ABC", "DEF", "GHI"])
  const nbr = ref(0);

  const name = computed(() => { return fn.value + " " + ln.value });

  const chgFn = () => {
    fn.value = "Gregory";
  }
  const toggleShowName = (tf) => {
    showName.value = !showName.value;
  }
  onMounted(() => {
    console.log("Mounted ...");
  })
  const inc = () => {
    nbr.value++;
  }
  watch(nbr, (x) => {
    console.warn("nbr has changed to ", x );
  });

  const McName = ref("Greg");
  const McDay = ref("Christmas Eve 2022");
  const McDom = ref(24);
</script>

<template>
  <CompProvideInject />
  <CompInheritClass style='color:green' />
  <MyComponent :name='McName' :day='McDay' :day-of-mo='McDom'  />
  <Header name='Gregory' />
  <div v-if='showName'>  
    <h1 >App.vue by {{ name }}</h1>
  </div>
  <div v-else>
    <h1 >Name is hidden</h1>
  </div>
  <button @click='chgFn'>Change</button>
  <button @click='toggleShowName'>Show/Hide Name</button>
  <div>
    <ul>
      <li v-for='(item, idx) in items'>
        {{ idx }} : {{  item }}
      </li>
    </ul>
  </div>
  <button @click='inc' class='btn btn-primary'>Increment</button>
</template>

<style scoped>
</style>

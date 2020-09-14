<template>
  <div id="app">
    <hello-world2 :columns="columns" :items="dataSource"></hello-world2>
    <button @click="add">Click Add</button>
  </div>
</template>

<script>
import HelloWorld2 from './components/HelloWorld2.vue'
import faker from "faker";

export default {
  name: 'App',
  components: {
    HelloWorld2
  },
  data() {
    const source = []
    for (let i = 0; i < 50; i++) {
      source.push({
        id: Math.random().toString(),
        firstName: faker.name.firstName(),
        lastName: faker.name.lastName(),
        phoneNumber: faker.phone.phoneNumber(),
        fileName: faker.system.fileName(),
        ip: faker.internet.ip()
      });
    }

    return {
      msg: "Welcome to Your Vue.js App",
      dataSource: source,
      columns: [
        "id", "firstName", "lastName", "phoneNumber", "fileName", "ip"
      ]
    }
  },
  methods: {
    add() {
      const index = Math.floor(Math.random() * 50);
      this.dataSource[49].firstName = faker.name.firstName();
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<script>
  export default {
    data () {
      return {
        name: 'Samundra Dhakal',
        status: 'active',
        tasks: ['Task One', 'Task Two', 'Task Three'],
        link: 'https://www.google.com',

      };
    },
    methods: {
      toggleStatus() {
        if (this.status === 'active') {
          this.status = 'pending';
        } else if (this.status === 'pending') {
          this.status = 'inactive';
        } else {
          this.status = 'active';
        }
      }
    }
  };
</script>

<template>
  <h1> {{name}}</h1>
  <p v-if="status=== 'active'"> user is active </p>
  <p v-else-if="status=== 'pending'">User is pending</p>
  <p v-else> user is inactive </p>

  <h3>Tasks: </h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{task}}</li>
  </ul>
  <a :href="link"> Click for Google</a>
  <br/>
  <button @click="toggleStatus">Change status</button>
</template>


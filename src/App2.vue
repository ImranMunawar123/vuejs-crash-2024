<script>
export default {
  data(){
    return{
      'name': 'John Doe',
      'status': 'active',
      'tasks': [
        'Task1',
        'Task2',
        'Task3'
      ],
      'link': 'https://www.google.com/'
    }
  },
  methods:{
    toggleStatus(){
      if(this.status == 'active'){
        this.status = 'pending';
      }else if(this.status == 'pending'){
        this.status = 'inactive';
      }else{
        this.status = 'active'
      }
    }
  }
}

</script>

<template>
  <h1>{{ name }}</h1>
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else>User is inactive</p>

  <h2>Tasks:</h2>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>

  <!-- <a v-bind:href=link>Visit Google</a> -->
  <a :href="link">Visit Google</a>

  <br>
  <button @click="toggleStatus">Toggle status</button>
</template>

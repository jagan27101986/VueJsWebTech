<template>
  <div class="content">
    <Header></Header>
    <CoursesStatus ></CoursesStatus>

  </div>
</template>

<script>
import Header from './Header.vue'
import CoursesStatus from './CoursesStatus.vue'

export default {
  name: 'Courses',

  components: {
    Header,
    CoursesStatus
  },

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>

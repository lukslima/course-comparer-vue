<template>
  <section class="container">
    <div>
      <h1 class="title">
        Comparador de Carreiras
      </h1>
    </div>

    <div>
      <b-row>
        <b-col v-for="courseNumber in courseNumbers" :key="courseNumber">
          <CourseSearch 
            :courseNumber="courseNumber"
          />
        </b-col>
      </b-row>
    </div>
  </section>
</template>

<script>
import CourseSearch from '~/components/course-search';

export default {
  components: {
    CourseSearch
  },
  data() {
    return {
      courseNumbers: [1, 2],
    }
  }
}
</script>

<style>
</style>

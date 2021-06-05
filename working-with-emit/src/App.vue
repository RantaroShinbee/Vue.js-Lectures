<template>
  <div id="app" class="container-fluid">
    <the-table
    :itemList="itemList"
    @add-one-student="addOneStudent">
    </the-table>
  </div>
</template>

<script>
import TheTable from './components/TheTable.vue';

export default {
  name: 'App',
  components: {
    TheTable
  },
  data() {
    return {
      itemList: [
        {
          id: 1,
          nickName: 'abc',
          age: 13,
          school: 'Spensivinia Primary School',
          favourite: 'play hockey',
          home: 'Yankee'
        }
      ]
    }
  },
  methods: {
    addOneStudent(student) {
      var item = {
        id: (this.itemList.length + 1),
        nickName: student.nickName,
        age: student.age,
        school: student.school,
        favourite: student.favourite,
        home: student.home,
      }
      this.itemList.push(item);
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

<template>
  <div class="about">
    <h1>已修选修课程</h1>
    <p>欢迎您，{{name}}</p>
    <br>
    <button @click="add_course()">添加课程</button>
    <br>
    <table border="1" class="Table">
    <tr>
    <th>课程名称</th>
    <th>授课教师</th>
    <th>学分</th>
    </tr>
    <tr v-for="(course_for,index) of course_list" :key="index">
    <td>{{course_for.course_name}}</td>
    <td>{{course_for.course_teacher}}</td>
    <td>{{course_for.course_point}}</td>
    </tr>
    </table>
  </div>
</template>
<script>
export default {
  name: 'select_point_table',
  data () 
  {	
  return{
  name: "猪猪侠",
  course_data:
  {
  course_name: "语文",
  course_teacher: "缪老师",
  course_point: 3,
  },
  course_list:
  [
  {
  course_name: "数学",
  course_teacher: "孔老师",
  course_point: 2,
  },
  {
  course_name: "英语",
  course_teacher: "程老师",
  course_point: 2,
  },
  {
  course_name: "物理",
  course_teacher: "李老师",
  course_point: 2,
  }
  ]
  }
  },
  
  methods: 
  {
  
  add_course()
  {
  this.course_list.unshift(this.course_data);
  },
  
  }
}
</script>
<style>
.div_back
{
background:url(../assets/course_table_background.jpg) no-repeat 150px
}
.Table
{
height:100%;
margin: 0 auto;
width:100%;
}
table, td, th
  {
  border:1px solid green;
  }
th
  {
  background-color:green;
  color:white;
  }
</style>
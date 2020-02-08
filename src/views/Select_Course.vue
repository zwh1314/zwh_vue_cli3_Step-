<template>
  <div class="about">
    <h1>选择课程</h1>
    <p>欢迎您，{{name}}</p>
    <br>
    <button @click="add_course()">添加课程</button>
    <br>
    <table border="1" class="Table">
    <tr>
    <th>课程名称</th>
    <th>授课教师</th>
    <th>学分</th>
    <th>课程已选人数/课程上限人数</th>
    <th>
	点击选课
    </th>
    </tr>
    <tr v-for="(course_for,index) of course_list" :key="index">
    <td><router-link to="/course_inf" @click.native="check_course_inf(course_for)">{{course_for.course_name}}</router-link></td>
    <td>{{course_for.course_teacher}}</td>
    <td>{{course_for.course_point}}</td>
    <td>{{course_for.course_number}}</td>
    <td>
    <button @click="select_course(course_for,index)">选课</button>
    </td>
    </tr>
    </table>
  </div>
</template>
<script>
import {mapMutations} from 'vuex' //获取./store中state中的变量和mutations中的函数

export default {
  name: 'my_classtable_ready',
  data () 
  {	
  return{
  name: "猪猪侠",
  course_data:
  {
  course_name: "语文",
  course_teacher: "缪老师",
  course_point: 3,
  course_number: "30/32",
  },
  course_list:
  [
  {
  course_name: "数学",
  course_teacher: "孔老师",
  course_point: 2,
  course_number: "16/25",
  },
  {
  course_name: "英语",
  course_teacher: "程老师",
  course_point: 2,
  course_number: "19/18",
  },
  {
  course_name: "物理",
  course_teacher: "李老师",
  course_point: 2,
  course_number: "20/21",
  }
  ]
  }
  },
  
  methods: 
  {
  ...mapMutations(["check_course_inf"]),
  
  add_course()
  {
  this.course_list.unshift(this.course_data);
  },
  
  select_course(course_for,index)
  {
  let str_split=course_for.course_number.split('/');
  if(parseInt(str_split[0])>=parseInt(str_split[1])){
  //如何人数达到了上限
  alert("该课程已选人数已达上限，请选择其他课程！");
  return;
  }
  else if(window.confirm("您确定选择此门课程吗？"))
  {
  //将课程上传到个人数据库
  alert("选课成功！");
  this.course_list.splice(index,1);
  }
  }
  
  }
}
</script>
<style>
a:link {color: black;  font-weight: bold;} /*平时链接的样式*/ 
a:hover {color: blue;  font-weight: bold;} /*鼠标放置在链接上方的样式*/ 
a:visited {color: black;  font-weight: bold;} /*访问过后的样式*/ 

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
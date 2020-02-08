<template>
  <div class="about">
    <h1>个人信息</h1>
    <table border="1" align="center">
		<tbody>
			<tr>
				<th colspan="4">个人信息</th>
			</tr>
			<tr>
				<td>姓名</td>
				<td colspan="2">{{name}}</td>
				
				<td rowspan="4">
				<input type="file" >
				</td>
			</tr>
			<tr>
				<td>联系方式</td>
				<td colspan="2">{{telephone}}</td>
				
			</tr>
			<tr>
				<td>一级学院</td>
				<td colspan="2">{{department}}</td>

			</tr>
			<tr>
				<td>学号</td>
				<td colspan="2">{{student_id}}</td>
			</tr>
			<tr>
				<td>性别</td>
				<td width="100">{{sex}}</td>
				<td>结班时间</td>
				<td width="100">{{end_time}}</td>
			</tr>
			<tr>
				<td>班级</td>
				<td width="100">{{class_number}}</td>
				<td>入党状态</td>
				<td width="100">{{party_status}}</td>
			</tr>
		</tbody>
    </table>
  </div>
</template>

<script>
export default {
  name: 'student_inf',
  data () 
  {	
  return{
  name: "张文瀚",
  telephone: "",
  department: "",
  student_id: "",
  sex: "",
  class_number: "",
  end_time: "",
  party_status: "",
  }
  },
}
</script>

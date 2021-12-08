<template>
    <div>
        <el-form ref="form" :model="form" label-width="80px">
            <el-form-item label="活动名称">

                <el-input v-model="form.name"></el-input>  <el-button type="primary" @click="onSubmit(form.name)">搜索</el-button>

            </el-form-item>

        </el-form>
        <el-table
        :data="tableData"
        style="width: 100%"

        >
        <el-table-column
            prop="date"
            label="日期"
            width="180">
        </el-table-column>
        <el-table-column
            prop="name"
            label="姓名"
            width="180">
        </el-table-column>
        <el-table-column
            prop="address"
            label="地址">
        </el-table-column>
        <el-table-column

            label="操作">

              <template slot-scope="scope">
                <el-button type="danger" icon="el-icon-delete" @click="onDelete(scope.$index)" >删除</el-button>
              </template>


        </el-table-column>


        </el-table>
    </div>
</template>
<style scoped>

</style>
<script>
export default {
     data() {
        return {
          form:{
               name: '',
          },
          tableData: [{
            date: '2016-05-02',
            name: '王小虎0',
            address: '上海市普陀区金沙江路 1518 弄'
          }, {
            date: '2016-05-04',
            name: '王小虎1',
            address: '上海市普陀区金沙江路 1517 弄'
          }, {
            date: '2016-05-01',
            name: '王小虎2',
            address: '上海市普陀区金沙江路 1519 弄'
          }, {
            date: '2016-05-03',
            name: '王小虎3',
            address: '上海市普陀区金沙江路 1516 弄'
          }]
        }
      },
      methods:{
          onSubmit(index){
              alert(index);

              this.tableData=this.tableData.slice(2,1)
          },
          onDelete(index){
              alert(index);
               this.tableData.splice(index,1)
          }
      }
}
</script>

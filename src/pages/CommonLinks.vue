<!-- 参考：https://github.com/PanJiaChen/vue-element-admin/blob/master/src/views/table/inline-edit-table.vue-->

<template>
  <div class="app-container">
    <el-table
      v-loading="listLoading"
      :data="list"
      border
      fit
      highlight-current-row
      style="width: 100%"
    >
      <el-table-column align="center" label="ID" width="80">
        <template slot-scope="{ row }">
          <span>{{ row.id }}</span>
        </template>
      </el-table-column>

      <el-table-column width="180px" align="center" label="URL">
        <template slot-scope="{ row }">
          <a target="_blank" :href="row.url">
            <el-link type="info" @click="goTo(row.url)">{{ row.url }}</el-link>
          </a>
        </template>
      </el-table-column>

      <el-table-column width="180px" align="center" label="描述">
        <template slot-scope="{ row }">
          <span>{{ row.desc }}</span>
        </template>
      </el-table-column>

      <el-table-column align="center" label="Actions" width="120">
        <template slot-scope="{ row }">
          <el-button
            v-if="row.edit"
            type="success"
            size="small"
            icon="el-icon-circle-check-outline"
            @click="confirmEdit(row)"
          >
            Ok
          </el-button>
          <el-button
            v-else
            type="primary"
            size="small"
            icon="el-icon-edit"
            @click="row.edit = !row.edit"
          >
            Edit
          </el-button>
        </template>
      </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  // methods:{
  //   goTo(e) {
  //     window.location.href = e
  //   }
  // },
  data() {
    return {
      list: [
        {
          id: "1",
          url: "http://www.baidu.com",
          desc: "百度"
        },
        {
          id: "2",
          url: "http://www.qq.com",
          desc: "QQ"
        },
        {
          id: "3",
          url: "http://www.taobao.com",
          desc: "淘宝"
        }
      ]
    };
  }
};
</script>

<style scoped></style>

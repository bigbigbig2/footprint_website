<template>
    <s-table :data="data" :loading="listLoading" :columns="columns" @query-change="getList">
    </s-table>
</template>
<script>
import STable from '@/components/Table'

export default {
  components: { STable },
  data() {
    return {
      columns: [
        {
          label: '序号',
          field: 'id',
          width: 90
        },
        {
          label: '账号',
          field: 'account',
          width: 160
        },
        {
          label: '公司名称',
          field: 'companyName'
        },
        {
          label: 'accessKey',
          field: 'accessKey',
          width: 180
        },
        {
          label: '秘钥',
          field: 'secret',
          width: 180
        }
      ],
      data: null,
      listLoading: false,
      listQuery: {}
    }
  },
  created() {},
  methods: {
    handleFilter() {
      this.listQuery.page = 1
      this.getList()
    },

    getList(evt) {
      if (evt) {
        Object.assign(this.listQuery, evt)
      }
      this.listLoading = true
     // 请求后端
      fetchList(this.listQuery).then(response => {
        this.data = response
        this.listLoading = false
      })
    }
  }
}
</script>
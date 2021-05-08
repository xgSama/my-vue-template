<template>
  <el-table :data="list" style="width: 100%;padding-top: 15px;">
    <el-table-column label="Order_No" min-width="200">
      <template slot-scope="scope">
        <router-link to="/form">{{ scope.row.order_no | orderNoFilter }}</router-link>
      </template>
    </el-table-column>
    <el-table-column label="Price" width="195" align="center">
      <template slot-scope="scope">
        ¥{{ scope.row.price | toThousandFilter }}
      </template>
    </el-table-column>
    <el-table-column label="Status" width="100" align="center">
      <template slot-scope="{row}">
        <el-tag :type="row.status | statusFilter">
          {{ row.status }}
        </el-tag>
      </template>
    </el-table-column>
  </el-table>
</template>

<script>
export default {
  filters: {
    statusFilter(status) {
      const statusMap = {
        success: 'success',
        pending: 'danger'
      }
      return statusMap[status]
    },
    orderNoFilter(str) {
      return str.substring(0, 30)
    },
    toThousandFilter(str) {
      return str
    }
  },
  data() {
    return {
      list: [
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E94',
          timestamp: '2020-1-1',
          username: '1111111',
          price: 150.2,
          status: 'pending'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: '已完成'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        },
        {
          order_no: '1bf57B81-D3e9-b9C4-ecDd-856E95',
          timestamp: Date.now,
          username: '11112222111',
          price: 32232.3,
          status: 'success'
        }
      ]
    }
  },
  created() {
    // this.fetchData()
  },
  methods: {

  }
}
</script>

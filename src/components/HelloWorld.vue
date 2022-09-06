<template>
  <div>
    <el-button type="primary" @click="sendGet">发送GET请求</el-button>
    <el-button type="success" @click="sendPost">发送POST请求</el-button>
    <el-button type="warning" @click="sendPut">发送PUT请求</el-button>
    <el-button type="danger" @click="sendDelete">发送DELETE请</el-button>
  </div>
</template>
<script>
import axios from "axios"
export default {
  name: "HelloWorld",
  methods: {
    sendGet() {
      axios({
        method: "GET",
        url: "http://localhost:3000/posts/1"
      }).then(response => {
        console.log(response.data)
      })
    },
    sendPost() {
      axios({
        method: "POST",
        url: "http://localhost:3000/posts",
        data: {
          title: "Hello World",
          author: "张三"
        }
      }).then(response => {
        console.log(response.data)
      })
    },
    sendPut() {
      axios({
        method: "PUT",
        url: "http://localhost:3000/posts/2",
        data: {
          title: "Hello World",
          author: "李四"
        }
      }).then(response => {
        console.log(response.data)
      })
    },
    sendDelete() {
      axios({
        method: "DELETE",
        url: "http://localhost:3000/posts/2"
      }).then(response => {
        console.log(response.data)
      })
    }
  }
}
</script>

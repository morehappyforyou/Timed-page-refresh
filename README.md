# Timed-page-refresh
# js 页面定时刷新
<script>
  export default{
  data:{
    timer:"",  
  }
  }
mounted() {
    this.dealWithTime(new Date())
    if(this.timer){
       clearInterval(this.timer)  //timer在data里面定义，字符串格式：timer:"",
     } else{
        this.timer = setInterval(() => {
            this.refreshRealData();  // 调用相应的接口，渲染数据 
        },30000) //延时30秒
      }
 },  
destroyed(){
   clearInterval(this.timer) 
}
</script>

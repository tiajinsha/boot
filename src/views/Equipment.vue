<template>
    <div class="Exhibition">
    <van-nav-bar title="组织架构" left-text="wad" fixed >
    <van-icon name="arrow-left
" slot="left" @click="location" />
    </van-nav-bar>
        <div v-html="list.info"></div>
         <fenxiang title="#/Equipment"></fenxiang>
        <abc></abc>
    </div>
</template>
<script>
import fenxiang from '../components/fenxiang'
import abc from '../components/text'
export default {
    data(){
        return{
            list:[]
        }
    },
    created(){
        this.msg()
    },methods:{
        location(){
               this.$router.go(-1)
        },
        msg(){
            var url="/getOrganization"
            this.axios.post(url).then(result=>{
                this.list=result.data.data
            })
        }
    },
    components:{
     /*   touchBar, */
       fenxiang,
       abc 
    }
}
</script>
<style lang="scss" scoped>
    .Exhibition{
        width:90%;
        height:500px;
        margin: 0 auto;
        margin-top: 55px;
        div{
                font-size: 0.4rem;
                font-family: PingFang-SC-Bold;
                color: #333333;
        }
    }
</style>
<template>
  <div>
        <!-- <div :class='{"all-bg":allbg}' v-for="(item, index) in arr"  @click="showCloud(index)"> -->
        <div :class='allbg' v-for="(item, index) in arr"  @click="showCloud(index)">
            <a href="item"></a>
        </div>
  </div>
</template>

<script>
export default {
    data(){
        return{
            arr:[1,2,3,4,5,6,7,8,9],
            cloud:false,
            allbg:"all-bg",
        }
    },
    created(){
        this.$nextTick(()=>{
            this.showCloud(0);
        })
    },
    methods:{
        showCloud(index){
            console.log(index)
            console.log(this.$el);
            var colud=this.$el.querySelectorAll(".all-bg");
            for(var i=0;i<colud.length;i++){
                colud[i].className='all-bg';
            }
            colud[index].className="all-bg bg-cloud";
        } 
    }
}
</script>

<style>
    .bg-cloud{
        float: left;
        margin: 10px;
        width: 100px;
        height: 100px;
        background: pink !important;
    }
    .all-bg{
        background: black;
        float: left;
        margin: 10px;
        width: 100px;
        height: 100px;
    }
</style>

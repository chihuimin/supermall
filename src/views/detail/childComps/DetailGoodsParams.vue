<template>
    <div class="param-info" v-if="Object.keys(paramsInfo).length !== 0" >
        <table  v-for="(table,index) in paramsInfo.sizes" :key="index" class="info-size">
            <tr v-for="(tr,num) in table" :key="num">
                <td v-for="(td,i) in tr" :key="i">{{td}}</td>
            </tr>
        </table>
        <table class="info-param" >
            <tr v-for="(info,j) in paramsInfo.infos" :key="j">
                <td class="info-param-key">{{info.key}}</td>
                <td class="param-value">{{info.value}}</td>
            </tr>
        </table>
        <div class="info-img" v-if="paramsInfo.image!==0">
            <img :src="paramsInfo.image" alt="">
        </div>
    </div>
</template>

<script>
export default {
    props:{
        paramsInfo:{
            type:Object,
            default(){
                return {}
            }
        }
    }

}
</script>


<style scoped>
    .param-info {
    padding: 20px 15px;
    font-size: 14px;
    border-bottom: 5px solid #f2f5f8;
  }

  .param-info table {
    width: 100%;
    border-collapse: collapse;
  }

  .param-info table tr {
    height: 42px;
  }

  .param-info table tr td {
    border-bottom: 1px solid rgba(100,100,100,.1);
  }

  .info-param-key {
    /*当value的数据量比较大的时候, 会挤到key,所以给一个固定的宽度*/
    width: 95px;
  }

  .info-param {
    border-top: 1px solid rgba(0,0,0,.1);
  }

  .param-value {
    color: #eb4868
  }

  .info-img img {
    width: 100%;
  }
</style>

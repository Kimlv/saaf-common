/*
 * @Author: zhengxiaowen; 357280841@qq.com; 
 * @Date: 2020-01-05 11:54:44 
 * @Last Modified by: zhengxiaowen
 * @Last Modified time: 2020-01-05 17:51:54
 */
/*
 * @Author: zhengxiaowen; 357280841@qq.com; 
 * @Date: 2020-01-05 11:54:44 
 * @Last Modified by: zhengxiaowen
 * @Last Modified time: 2020-01-05 12:50:57
 */


<template>
    <div>
        <div>
            <div id="SaafGooFlow"></div>
        </div>
    </div>
</template>
<script>
import * as GooFlow from '../../plugins/GooFlow/plugin/GooFlow.min'
import '../../plugins/GooFlow/plugin/GooFlow.less'
import api from '../../config/apiCommon'
import { mapState } from 'vuex'
    export default {
      props:{
        flow: Object,
        width: String | Number,
        height: String | Number
      },
      components: {
      },
      data () {
        return {
        }
      },
     computed: {
        ...mapState({
            certificate: state => state.user.certificate
        }),
      },
      created(){
        
      },
      mounted () {
          GooFlow.processImageDraw(api.bpmProcessService_getGooflowProcessJSON, this.certificate, 'SaafGooFlow', this.width, this.height, this.flow)
      },
      methods: {
          refreshGooflow(width,height){
              GooFlow.processImageDraw(api.bpmProcessService_getGooflowProcessJSON, this.certificate, 'SaafGooFlow', width, height, this.flow)
          }
      }
    }
</script>
<style lang="less" scoped>
</style>

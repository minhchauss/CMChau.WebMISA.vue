<template>
    <div id="dialogConfirmDelete" class="dialog" v-bind:class="{'dialog-hide':isShow}">
        <div class="model"></div>
        <div class="dialog-content">
            <div class="dialog-body">
                <p>{{ message }}</p>
            </div>
            <div class="dialog-footer">
                <button class="btn-default btn-cancel" v-on:click="btnOnCancel()">Hủy</button>
                <button id="btnConfirmDelete" class="btn-default" v-on:click="btnOnConfirmOk()">OK</button>
            </div>
        </div>
    </div>
</template>



<script>
import axios from 'axios';
export default {
    props:{
        isShow:{
            type:Boolean,
            default:true,
        },
        idCustomer:{
            type:String,
            default:null,
        },
        
    },

    //các hàm tương tác với với form xác nhận sửa xóa
    methods:{
      btnOnCancel(){
          this.$emit("hideDialogDetail", false);
      }  ,
      btnOnConfirmOk(){
        this.$emit("hideDialogDetail", false);

        axios.delete("http://api.manhnv.net/api/customers/"+this.idCustomer).then(()=>{
       this.reLoadCustomer();
        // alert(this.idCustomer);
      })
      },
      reLoadCustomer(){
          this.$emit('reLoadData');
      }
    },
    data() {
        return {
            message:'Bạn chắc chắn muốn xóa không?',
            customer:{},
        }
    },
}
</script>
<style scoped>
@import url(../../../assets/css/CommonCss/dialog.css);
@import url(../../../assets/css/CustomerCss/customer.css);
</style>
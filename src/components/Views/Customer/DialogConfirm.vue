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
       if(this.formMode=="Add"){
           alert("thêm");
       }
       else if(this.formMode=="Edit"){
           alert("Sửa");
        //     axios
        //   .put(
        //     "http://api.manhnv.net/api/customers/" + this.idCustomer,
        //     this.customer
        //   )
        //   .then((res) => {
        //     this.reLoadCustomer();
        //     this.$emit('btnOnCloseClick');
        //     this.$emit("hideDialogDetail", false);
        //     console.log(res);
        //     this.message="Bạn có chắc muốn sửa"
        //   })
        //   .catch((res) => {
        //     console.log(res);
        //   });
       }
       else{
        this.$emit("hideDialogDetail", false);

        axios.delete("http://api.manhnv.net/api/customers/"+this.idCustomer).then(()=>{
       this.reLoadCustomer();
        this.message="Bạn có chắc chắn muốn xóa";
      })
       }
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
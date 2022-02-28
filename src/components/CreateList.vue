<template>
    <div class="form-row mb-3">
        <div class="col-10">
            <input type="text" class="form-control form-control-lg" v-model="newMessage" @keyup.enter="create()"  @keyup="showE = false" placeholder="Say Something">
        </div>
        <div class="col-2">
            <button class="btn btn-primary btn-lg w-100" @click="create()">
                <i class="fas fa-plus-circle"></i>
            </button>
        </div>
         <div class="col-12">
                    <small v-if="showE">
                        {{errorMessage}}
                    </small>
                </div>
    </div>
               
</template>

<script>
    export default {
        name : "CreateList",
        data() {
            return {
                newMessage : "",
                showE : false,
                errorMessage : "error 404 not found"
            }
        },

        methods: {
            create() {
               if(this.newMessage.length){
                    this.$emit("createList",this.newMessage)
                 this.newMessage = "";
               }else{
                   this.showE = true
               }
            }
        },
    }
</script>

<style lang="scss" scoped>

</style>
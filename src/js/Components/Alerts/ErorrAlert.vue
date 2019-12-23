<template>
    <transition name="fade">
          <v-alert
          v-if="show"
          :value="true"
          icon="mdi-shield-lock-outline"
          prominent
          text
          type="info"
        ><p>{{ message }}</p>
        </v-alert>
    </transition>
</template>

<script>
    export default {
        name: "ErorrAlert",
        data:function () {
            return{
                show:false
            }
        },
        props:['message'],
        methods:{
            showAlert:function () {
                this.show  = true;
                window.setTimeout(()=>{this.show =false },3000)
            }
        },
    }
</script>

<style scoped lang="scss">
    .alert{
        padding: 15px;
    button,p{
        background: transparent;
        border: none;
        color:darken(#b71c1c,20%);
    }
    }

    .fade-enter-active, .fade-leave-active {
        transition: opacity .2s;
    }
    .fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
        opacity: 0;
    }
</style>
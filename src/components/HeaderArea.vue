<template>
    <div class="header">
        <div class="header-left">
            <logo-small />
        </div>
        <div class="header-right">
            <span>
                <bell-icon />
            </span>
            <img :src="avatar" alt="">
        </div>
    </div>
</template>
<script>
import Avatar from "../../public/assets/avatar-40.png";
import BellIcon from "./Icons/BellIcon.vue";
import LogoSmall from './Icons/LogoSmall.vue';

 export default{
    components:{
        BellIcon,
        LogoSmall,
    },
    data(){
        return{
            avatar: Avatar
        }
    }
 }
</script>
<style>
.header{
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 24px;
    background: white;
    z-index: 9;
    position: relative;
}
.header-right{
    display: inline-flex;
    align-items: center;
    gap: 16px;
}
</style>
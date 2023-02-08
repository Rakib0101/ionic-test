<template>
    <div class="header">
        <div class="header-left">
            <LogoLarge />
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
import LogoLarge from "./Icons/LogoLarge.vue";
import Avatar from "../../public/assets/avatar-40.png";
import BellIcon from "./Icons/BellIcon.vue";

 export default{
    components:{
        LogoLarge,
        BellIcon,
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
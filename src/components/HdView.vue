<template>
    <div class="header">
        <div class="logo">
            <img src="@/assets/logo.png">
            <div class="text">
                <span>新视觉实训</span>
                博客系统
            </div>
        </div>
        <div class="nav">
            <a href="#" >博客列表</a>
            <a href="#">添加博客</a>
        </div>
    </div>
</template>
<script>

export default {
}
</script>
<style lang="less" >
.header{
    height: 80px;
    background: #41B883;
    display: flex;
    justify-content: space-between;
    padding: 0 30px;
    align-items: center;
    .logo{
        display: flex;
        align-items: center;
        cursor:pointer;
        img{
            height: 100px;

        }
        .text{
            color: white;
            font-size: 20px;
            padding-left: 10px;
            span{
                display: block;
                font-size: 14px;
                opacity: 0.7;
            }
        }
    }
    .nav{
        display: flex;
        a{
            display: block;
            border-radius: 5px;
            padding: 5px 20px;
            color:white ;
            font-size: 18px;
            margin-left: 10px;
            &:hover,&:active{
                color: #41B883;
                background: white;
            }
        }
    }
}
</style>

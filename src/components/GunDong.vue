<template>
<div class="father_srcoll" ref="father_srcoll">
    <div class="child_scroll" ref="child_scroll">
        <div class="imgItem">
            <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
            <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
            <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
            <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
            <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
        <div class="imgItem">
            <img src="../assets/logo.png" class="img" style="margin: 0 10px;" />
        </div>
    </div>
</div>
</template>

<script>

import BScroll from 'better-scroll'

export default {
    data() {
        return {
            width: 0,
        }
    },
    created() {
        this.$nextTick(() => {//回调横向滚动方法
            this.personScroll();
        });
    },
    methods: {
        GetNum() {
            this.width = 120 * 3;
            return this.width;
        },//计算出横向滚动组件需要的总宽度

        personScroll() {
            this.$refs.child_scroll.style.width = this.GetNum() + "px";
            this.$nextTick(() => {
                if (!this.scroll) {
                    this.scroll = new BScroll(this.$refs.father_srcoll, {
                        startX: 0,
                        click: true,
                        scrollX: true,//
                        scrollY: false,
                        eventPassthrough: "vertical"
                    });
                } else {
                    this.scroll.refresh();
                }
            });
        },//横向滚动
    },
}
</script>

<style>
.father_srcoll{
    background-color: green;
    position: absolute;
    height: 100px;
    margin-top: 35px;
    margin-right: -10em;
    width: 100%;
    overflow: auto;
    z-index: 5;
}

.child_scroll {
    background-color: yellow;
    width: 100%;
    position: absolute;
    display: flex;
}
.child_scrolllll{
    background-color: yellow;
    width: 100%;
    position: absolute;
    display: flex;
}
.imgItem {
    background-color: rgb(74, 11, 31);
    margin-left: 1em;
}

</style>
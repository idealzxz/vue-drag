<template>
    <div class="drag" v-drag></div>
</template>
<script lang="ts">
Vue.directive('drag', {
    bind: function(el) {
        let odiv = el; //获取当前元素
        odiv.onmousedown = (e: any) => {
            //算出鼠标相对于元素的位置
            let disX = e.clientX - odiv.offsetLeft;
            let disY = e.clientY - odiv.offsetTop;

            document.onmousemove = (e: any) => {
                //用鼠标的当前屏幕位置 减去 鼠标相对于元素的位置，得到元素的位置
                let left = e.clientX - disX;
                let top = e.clientY - disY;

                //移动当前元素
                odiv.style.left = left + 'px';
                odiv.style.top = top + 'px';
            };
            document.onmouseup = (e: any) => {
                document.onmousemove = null;
                document.onmouseup = null;
            };
        };
    },
});
import { Vue, Component } from 'vue-property-decorator';
@Component
export default class Dragbind extends Vue {}
</script>
<style lang="scss" scoped>
.drag {
    width: 100px;
    height: 100px;
    background: red;
    position: absolute;
}
</style>

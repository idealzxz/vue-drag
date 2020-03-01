<template>
    <div
        @mousedown="handledown($event)"
        @mousemove.prevent="handlemove($event)"
        @mouseup="handleup($event)"
        class="drag"
        ref="drag"
    ></div>
</template>
<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
@Component
export default class Darg extends Vue {
    private offx = 0;
    private offy = 0;

    private x = 0;
    private y = 0;
    private drag = false;
    public handledown = (e: any) => {
        console.log(this.$refs.drag);
        const blockx = (this.$refs.drag as any).offsetLeft;
        const blocky = (this.$refs.drag as any).offsetTop;
        this.offx = e.clientX - blockx;
        this.offy = e.clientY - blocky;
        // 控制拖拽状态
        this.drag = true;
    };
    public handlemove = (e: any) => {
        this.x = e.pageX - this.offx;
        this.y = e.pageY - this.offy;

        if (this.drag) {
            e.target.style.left = this.x + 'px';
            e.target.style.top = this.y + 'px';
        }
        // console.log(this.x, this.y);
    };
    public handleup = (e: any) => {
        this.drag = false;
    };
}
</script>
<style lang="scss" scoped>
.drag {
    width: 100px;
    height: 100px;
    background: #cccccc;
    position: absolute;
}
</style>

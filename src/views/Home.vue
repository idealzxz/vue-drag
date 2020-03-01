<template>
    <div class="home">
        <Drag />
    </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import Drag from '@/components/Drag.vue';
@Component({ components: { Drag } })
export default class Home extends Vue {}
</script>

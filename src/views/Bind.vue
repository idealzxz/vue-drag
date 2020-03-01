<template>
    <div class="bind">
        <Dragbind />
    </div>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';
import Dragbind from '@/components/Dragbind.vue';
@Component({ components: { Dragbind } })
export default class Bind extends Vue {}
</script>

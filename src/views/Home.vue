<template>
  <div class="home">
    <data-table-info />
  </div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import DataTableInfo from '@/components/DataTableInfo.vue'; // @ is an alias to /src

@Component({
  components: {
    DataTableInfo,
  },
})
export default class Home extends Vue {}
</script>

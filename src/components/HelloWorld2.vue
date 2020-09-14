<template>
  <table border="1" cellspacing="0" cellpadding="0" style="width: 100%">
    <thead>
    <tr v-if="columns&&columns.length">
      <th v-for="col in columns">{{ col }}</th>
    </tr>
    </thead>
    <tbody>
    <tr v-for="item in items" :key="item.id">
      <td v-for="key in Object.keys(item)" :key="key">
        <!--        <el-input :value="item[key]"/>-->
        <d-input :value="item[key]" :data-id="key"/>
      </td>
    </tr>
    </tbody>
  </table>
</template>

<script>
import DInput from "@/components/DInput";

export default {
  name: "HelloWorld2",
  components: {DInput},
  props: {
    "columns": {
      type: Array,
      default: () => []
    },
    "items": {
      type: Array,
      default: () => []
    }
  }
}
</script>

<style scoped>

</style>

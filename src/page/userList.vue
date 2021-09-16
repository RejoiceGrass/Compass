<template>
    <div>
        <div class="updata">

          
        </div>
      </div>
</template>

<script>
export default {
    data() {
      const item = {
        date: '2020-07-28',
        name: '司凯乐',
        address: '上海杉达学院',
        number: '18662783632'
        
      };
      return {
        tableData: Array(20).fill(item),
        flag:false
      }
    },
}
</script>

<style>

</style>
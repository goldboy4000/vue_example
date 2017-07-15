<template>
  <div class="search">

    <p class="control has-icons-left has-icons-right">
      <input v-model="searchKey" class="input is-info" type="text" placeholder="search" value="">
      <span class="icon is-small is-left">
      <i class="fa fa-user"></i>
    </span>
      <span class="icon is-small is-right">
      <i class="fa fa-check"></i>
    </span>
    </p>
    <datagrid :data="info" :headers="headerNames" :searchkey="searchKey"></datagrid>

  </div>
</template>

<script>
  import DataGrid from '@/components/partials/DataGrid.vue'

  export default {
    name: 'search',
    components: {
      'datagrid': DataGrid
    },
    data () {
      return {
          info:[
              {name: 'Bruce Lee', power: 9000},
              {name: 'Chuck Norris', power: 8000},
              {name: 'Jackie Chan', power: 7000},
              {name: 'Jet Li', power: 7000}
          ],
          headerNames:[
            'Masters', 'Power'
          ],
          searchKey: ''
      }
    }
  }
</script>



<template>
  <div class="datagrid">

    <table class="table">
      <thead>
          <th v-for="item in headers">{{item}}</th>
      </thead>

      <tbody>
        <tr v-for="item in fitleredData">
          <td>{{item.name}}</td>
          <td>{{item.power}}</td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<script>
  export default {
    name: 'datagrid',
    props: {data:Array, headers:Array, searchkey:String},
    computed: {
      fitleredData: function () {

        return this.data.filter(function (item) {
            if (item.name.indexOf(this.searchkey) !== -1)
            {
                return item;
            }
        }.bind(this));
      }
    }
  }
</script>




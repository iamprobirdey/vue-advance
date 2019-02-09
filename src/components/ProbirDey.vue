<template>
  <div>
    <h1>Hii , I am from Pro</h1>

    <span>Let's create dynamic crud data</span>
    <div>
      <ul>
        <li v-for="(item,index) in itemForCrud">
          {{item.id}} --- {{item.value}} <button @click="crudItemClicked(index)">Delete</button>
        </li>
      </ul>
    </div>

    <button @click="check">Let's check</button>
  </div>
</template>

<script>
import mixins from '../mixins/mixins';
export default {
  data() {
    return {
      itemsForCrud: [
        {id: 1 , value: 'one'},
        {id: 2 , value: 'two'},
        {id: 3 , value: 'three'},
        {id: 4 , value: 'four'},
        {id: 5 , value: 'five'},
        {id: 6 , value: 'six'},
        {id: 7 , value: 'seven'},
        {id: 8 , value: 'eight'},
        {id: 9 , value: 'nine'},
        {id: 10 , value: 'ten'},
        {id: 11 , value: 'eleven'}
      ],
    }
  },
  methods: {
    crudItemClicked(index){
      this.itemsForCrud.splice(index,1);
      console.log('I am spliced');
    },
    check(){
      this.itemForCrud.push(this.dataSplicedValue);
    }
  },
  updated() {
      console.log('I am from updated');
  },
  mixins: [mixins]
}
</script>



<template>
  <div class="items">
    <ul class="list-group">
      <li class="list-group-item" v-for="item in items" :key="item.id">
        {{ item.name }}
      </li>
    </ul>
  </div>
</template>

<script>
import firestore from '@/firebase/firestore.js'

export default {
  data () {
    return {
      items: [],
    }
  },
  mounted () {
    firestore.collection('items').get().then(snapShot => {
      const array = [];
      snapShot.forEach(item => {
        array.push(item.data());
      });
      this.items = array
    });
  }
}
</script>

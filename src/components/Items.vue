<template>
  <div class="items">
    <table class="table table-striped">
      <thead>
        <tr>
          <th>#</th>
          <th scope="col">名称</th>
          <th scope="col">価格</th>
          <th scope="col">カテゴリー</th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="item in items" :key="item.id">
          <th scope="row">{{ item.id }}</th>
          <td>{{ item.name }}</td>
          <td>{{ item.price }}</td>
          <td>{{ item.category_id }}</td>
        </tr>
      </tbody>
    </table>
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
    firestore.collection('items').orderBy('id', 'asc').get().then(snapShot => {
      const array = [];
      snapShot.forEach(item => {
        array.push(item.data())
      })
      this.items = array
    })
  }
}
</script>

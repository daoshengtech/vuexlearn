<template>
  <div>
    <h2>{{msg}}</h2>
    <hr/>

    <h3>{{$store.state.a.count}}</h3>
    <p>
      <button @click="$store.commit('add',10)">+</button>
      <button @click="reduce">-</button>
    </p>
    <p>
      <button @click="addAction">+</button>
      <button @click="reduceAction">-</button>
    </p>
  </div>

</template>
<script>
  import store from '@/vuex/store';
  import { mapState,mapMutations,mapGetters } from 'vuex';
  export default {
    data(){
      return{
        msg:'Hello Vuex',

      }
    },

    computed:{
     // ...mapGetters(["count"])
      //...mapState(["count"])
      count(){
        return this.$store.state.a.count;
      }
    },
    methods:mapMutations([
      'add','reduce'
    ]),
    methods:{
      ...mapMutations([
        'add','reduce'
      ]),
      ...mapActions(['addAction','reduceAction'])
    },
    store

  }
</script>

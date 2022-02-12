<template>
  <div class="pages">
      <div class="item" v-on:click="prev()">
          Prev
      </div>
      <div class="item" v-on:click="next()">
          Next
      </div>
  </div>
</template>

<script>
import { useStore } from 'vuex'
    let counter = 1;
export default {


    setup() {
        const store = useStore()

        const filter = ((page) => {
            store.dispatch('pageNumber', page)
        })

        return {
            filter
        }    
    }
}
</script>

<style lang="scss">
.pages {
        width: 400px;
        margin: 0 auto;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        border-radius: 10px;
        overflow: hidden;
    .item {
        padding: 1rem 0.5rem;
        background-color: var(--background-card);
        text-align: center;
        cursor: pointer;
        &:hover {
            color: var(--text-orange);
        }
    }
}

</style>
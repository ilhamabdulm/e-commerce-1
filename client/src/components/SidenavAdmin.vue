<template>
  <div>
    <ul>
      <li :class="{ active: active === 'item' }" @click.prevent="getItems">
        All Items
      </li>
      <li :class="{ active: active === 'revenue' }" @click.prevent="getRevenue">
        Shop Income
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'SidenavAdmin',
  data() {
    return {
      active: 'item'
    }
  },
  methods: {
    getItems() {
      this.active = 'item'
      this.$router.push('/panel')
    },
    getTransaction() {
      this.active = 'transaction'
      this.$router.push('/panel/transaction')
    },
    getRevenue() {
      this.active = 'revenue'
      this.$router.push('/panel/income')
    }
  }
}
</script>

<style lang="scss" scoped>
div {
  width: 100%;
  height: 100%;
  background: #6200ea;
  ul {
    padding: 0;
    width: 100%;
    li {
      margin-left: 0;
      border-bottom: 2px solid white;
      width: 100%;
      padding: 20px;
      list-style: none;
      font-size: 22px;
      font-weight: 500;
      color: white;
      cursor: pointer;
    }
    li:hover {
      color: #6200ea;
      background: white;
    }
  }
}
.active {
  color: #6200ea;
  background: white;
}
</style>

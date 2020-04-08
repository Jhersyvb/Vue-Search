<template>
  <div>
    <div class="form-group">
      <label for="search" class="sr-only">Escribe tu búsqueda</label>
      <input type="text" id="search" v-model="search" class="form-control" />
    </div>
    <div class="form-row">
      <label class="form-check form-check-inline">
        <input type="radio" v-model="available" :value="true" /> Disponible
      </label>
      <label class="form-check form-check-inline">
        <input type="radio" v-model="available" :value="false" /> No disponible
      </label>
    </div>
  </div>
</template>

<script>
export default {
  computed: {
    search: {
      get() {
        return this.$store.state.filter.query
      },
      set(value) {
        this.$store.commit('SER_QUERY', value)
      }
    },
    available: {
      get() {
        return this.$store.state.filter.available
      },
      set() {
        this.$store.commit('SET_AVAILABLE')
      }
    }
  }
}
</script>

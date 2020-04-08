<template>
  <div>
    <div class="form-group">
      <label for="search" class="sr-only">Escribe tu búsqueda</label>
      <input type="text" id="search" v-model="search" class="form-control" />
    </div>
    <div class="d-flex justify-content-center">
      <div class="form-check mr-5">
        <input type="radio" id="available" v-model="available" :value="true" class="form-check-input" />
        <label for="available" class="form-check-label">Disponible</label>
      </div>
      <div class="form-check">
        <input type="radio" id="notAvailable" v-model="available" :value="false" class="form-check-input" />
        <label for="notAvailable" class="form-check-label">No disponible</label>
      </div>
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
        this.$store.commit('SET_QUERY', value)
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

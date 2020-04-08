<template>
  <div class="col-sm-6 mb-3">
    <div class="card">
      <div class="card-header text-center">
        <h5 class="card-title">{{ movie.title }}</h5>
        <h6 class="card-subtitle">Available: {{ movie.available ? '✔️' : '❌' }}</h6>
      </div>
      <div class="card-body">
        <div class="card-text">{{ movie.description | excerpt(150) }}</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    movie: {
      type: Object,
      required: true
    }
  },
  filters: {
    excerpt(str, limit) {
      return str.substring(0, Math.min(str.length, limit)) + '...'
    }
  }
}
</script>

<template>
  <div class="container mt-5">
    <h2 class="text-center mb-5" >Gerador de nomes</h2>
    <b-row>
        <b-col>
          <Prefixes />
        </b-col>
        <b-col>
          <suffixes />
        </b-col>
    </b-row>
    <Generator />
  </div>
</template>
<script>
import Prefixes from './components/Prefixes.vue'
import Suffixes from './components/Suffixes.vue'
import Generator from './components/Generator.vue'
export default {
  components: { Prefixes, Suffixes, Generator}
}
</script>

<style>
</style>